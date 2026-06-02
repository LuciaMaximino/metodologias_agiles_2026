# Ejercicio Nro: 13-TDD

## Enunciado
Tu tarea es desarrollar una aplicación informática utilizando la técnica TDD para gestionar una cuenta bancaria. La aplicación debe permitir a los usuarios abrir una cuenta, realizar depósitos, hacer retiros y transferir fondos entre cuentas. A continuación se detallan las etapas de desarrollo utilizando TDD:
Etapa 1: Especificación y prueba inicial
1. Especifica los requisitos básicos del sistema y las funcionalidades clave, como la apertura de cuenta, depósito de fondos, retiro de fondos y transferencia de fondos.
2. Escribe una prueba inicial que verifique si el sistema puede crear una instancia de una cuenta bancaria y obtener su saldo inicial.
Etapa 2: Desarrollo de las funcionalidades básicas
3. Implementa la funcionalidad para abrir una cuenta bancaria, asegurándote de que se cumplan los requisitos especificados. Ejecuta la prueba y verifica que pase correctamente.
4. Implementa la funcionalidad para realizar depósitos en una cuenta bancaria. Ejecuta las pruebas y verifica que pasen correctamente.
5. Implementa la funcionalidad para realizar retiros de una cuenta bancaria. Ejecuta las pruebas y verifica que pasen correctamente.
6. Implementa la funcionalidad para transferir fondos entre cuentas bancarias. Ejecuta las pruebas y verifica que pasen correctamente.
Etapa 3: Pruebas adicionales y mejoras
7. Escribe pruebas adicionales para cubrir casos de prueba específicos, como intentar retirar más dinero del disponible en una cuenta o transferir fondos a una cuenta inexistente.
8. Ejecuta todas las pruebas y verifica que pasen correctamente.
9. Refactoriza tu código si es necesario para mejorar su estructura, legibilidad y eficiencia.
10. Ejecuta todas las pruebas nuevamente para asegurarte de que el código refactorizado no haya introducido errores.
Etapa 4: Cobertura completa de pruebas
11. Asegúrate de que todas las funcionalidades del sistema estén cubiertas por pruebas automatizadas.
12. Examina los casos límite y situaciones excepcionales para garantizar que el sistema se comporte correctamente en todos los escenarios.
13. Ejecuta todas las pruebas y verifica que pasen correctamente.
Recuerda seguir el enfoque TDD, donde agregarás una prueba antes de implementar cada funcionalidad y verificarás que todas las pruebas pasen antes de pasar a la siguiente etapa.
Esto te ayudará a desarrollar una aplicación confiable, mantenible y que cumpla con los requisitos establecidos.

## Resolución
bank_account.py
 
class InsufficientFundsError(Exception):
    """Se lanza cuando se intenta retirar más dinero del disponible."""
    pass
 
 
class AccountNotFoundError(Exception):
    """Se lanza cuando se intenta operar con una cuenta inexistente."""
    pass
 
 
class BankAccount:
    def __init__(self, owner: str, initial_balance: float = 0.0):
        if initial_balance < 0:
            raise ValueError("El saldo inicial no puede ser negativo.")
        self.owner = owner
        self._balance = initial_balance
 
    @property
    def balance(self) -> float:
        return self._balance
 
    def deposit(self, amount: float) -> None:
        if amount <= 0:
            raise ValueError("El monto a depositar debe ser mayor a cero.")
        self._balance += amount
 
    def withdraw(self, amount: float) -> None:
        if amount <= 0:
            raise ValueError("El monto a retirar debe ser mayor a cero.")
        if amount > self._balance:
            raise InsufficientFundsError(
                f"Fondos insuficientes: saldo actual ${self._balance:.2f}, "
                f"retiro solicitado ${amount:.2f}."
            )
        self._balance -= amount
 
    def transfer_to(self, target: "BankAccount", amount: float) -> None:
        if target is None:
            raise AccountNotFoundError("La cuenta destino no existe.")
        self.withdraw(amount)   # reutiliza validación de fondos
        target.deposit(amount)
 
    def __repr__(self) -> str:
        return f"BankAccount(owner={self.owner!r}, balance={self._balance:.2f})"
 

Tests TDD para la aplicación de Cuenta Bancaria 
test_bank_account.py

import pytest
from bank_account import BankAccount, InsufficientFundsError, AccountNotFoundError
 

- ETAPA 1: Especificación y prueba inicial 
class TestWhenCreatingABankAccount:
    """Pruebas sobre la apertura de una cuenta bancaria."""
 
    def test_should_create_account_with_owner_name(self):
        account = BankAccount("Ana García")
        assert account.owner == "Ana García"
 
    def test_should_have_zero_balance_by_default(self):
        account = BankAccount("Ana García")
        assert account.balance == 0.0
 
    def test_should_accept_initial_balance(self):
        account = BankAccount("Ana García", initial_balance=500.0)
        assert account.balance == 500.0
 
    def test_should_raise_error_with_negative_initial_balance(self):
        with pytest.raises(ValueError):
            BankAccount("Ana García", initial_balance=-100.0)
 
 
- ETAPA 2: Desarrollo de las funcionalidades básicas 
class TestWhenDepositingFunds:
    """Pruebas sobre depósitos en la cuenta."""
 
    def setup_method(self):
        self.account = BankAccount("Luis Torres", initial_balance=100.0)
 
    def test_should_increase_balance_after_deposit(self):
        self.account.deposit(200.0)
        assert self.account.balance == 300.0
 
    def test_should_allow_multiple_deposits(self):
        self.account.deposit(50.0)
        self.account.deposit(50.0)
        assert self.account.balance == 200.0
 
    def test_should_raise_error_when_deposit_amount_is_zero(self):
        with pytest.raises(ValueError):
            self.account.deposit(0)
 
    def test_should_raise_error_when_deposit_amount_is_negative(self):
        with pytest.raises(ValueError):
            self.account.deposit(-50.0)
 
 
class TestWhenWithdrawingFunds:
    """Pruebas sobre retiros de la cuenta."""
 
    def setup_method(self):
        self.account = BankAccount("María López", initial_balance=500.0)
 
    def test_should_decrease_balance_after_withdrawal(self):
        self.account.withdraw(200.0)
        assert self.account.balance == 300.0
 
    def test_should_allow_withdrawal_of_entire_balance(self):
        self.account.withdraw(500.0)
        assert self.account.balance == 0.0
 
    def test_should_raise_error_when_amount_is_zero(self):
        with pytest.raises(ValueError):
            self.account.withdraw(0)
 
    def test_should_raise_error_when_amount_is_negative(self):
        with pytest.raises(ValueError):
            self.account.withdraw(-100.0)
 
 
class TestWhenTransferringFunds:
    """Pruebas sobre transferencias entre cuentas."""
 
    def setup_method(self):
        self.origin = BankAccount("Carlos Ruiz", initial_balance=1000.0)
        self.destination = BankAccount("Sofía Pérez", initial_balance=200.0)
 
    def test_should_decrease_origin_balance_after_transfer(self):
        self.origin.transfer_to(self.destination, 300.0)
        assert self.origin.balance == 700.0
 
    def test_should_increase_destination_balance_after_transfer(self):
        self.origin.transfer_to(self.destination, 300.0)
        assert self.destination.balance == 500.0
 
    def test_should_keep_total_money_constant_after_transfer(self):
        total_before = self.origin.balance + self.destination.balance
        self.origin.transfer_to(self.destination, 400.0)
        total_after = self.origin.balance + self.destination.balance
        assert total_before == total_after
 
 
- ETAPA 3: Pruebas adicionales y mejoras
class TestWhenWithdrawingMoreThanAvailable:
    """Prueba retirar más dinero del disponible."""
 
    def test_should_raise_insufficient_funds_error(self):
        account = BankAccount("Pedro Díaz", initial_balance=100.0)
        with pytest.raises(InsufficientFundsError):
            account.withdraw(150.0)
 
    def test_should_not_modify_balance_on_failed_withdrawal(self):
        account = BankAccount("Pedro Díaz", initial_balance=100.0)
        with pytest.raises(InsufficientFundsError):
            account.withdraw(150.0)
        assert account.balance == 100.0  # el saldo no debe cambiar
 
    def test_should_raise_error_when_transferring_more_than_available(self):
        origin = BankAccount("Pedro Díaz", initial_balance=100.0)
        destination = BankAccount("Laura Gómez", initial_balance=0.0)
        with pytest.raises(InsufficientFundsError):
            origin.transfer_to(destination, 200.0)
 
    def test_should_not_modify_balances_on_failed_transfer(self):
        origin = BankAccount("Pedro Díaz", initial_balance=100.0)
        destination = BankAccount("Laura Gómez", initial_balance=50.0)
        with pytest.raises(InsufficientFundsError):
            origin.transfer_to(destination, 200.0)
        assert origin.balance == 100.0
        assert destination.balance == 50.0  # destino tampoco cambia
 
 
class TestWhenTransferringToNonExistentAccount:
    """Prueba transferir a una cuenta inexistente."""
 
    def test_should_raise_account_not_found_error(self):
        account = BankAccount("Elena Vega", initial_balance=500.0)
        with pytest.raises(AccountNotFoundError):
            account.transfer_to(None, 100.0)
 
    def test_should_not_modify_balance_on_failed_transfer_to_none(self):
        account = BankAccount("Elena Vega", initial_balance=500.0)
        with pytest.raises(AccountNotFoundError):
            account.transfer_to(None, 100.0)
        assert account.balance == 500.0


- ETAPA 4: Cobertura completa de pruebas
class TestWhenExecutingCombinedOperations:
    """Escenarios que combinan varias operaciones para verificar consistencia."""
 
    def test_should_handle_deposit_then_withdrawal_correctly(self):
        account = BankAccount("Javier Mora", initial_balance=0.0)
        account.deposit(1000.0)
        account.withdraw(250.0)
        account.withdraw(250.0)
        assert account.balance == 500.0
 
    def test_should_handle_chain_of_transfers(self):
        a = BankAccount("A", initial_balance=300.0)
        b = BankAccount("B", initial_balance=0.0)
        c = BankAccount("C", initial_balance=0.0)
        a.transfer_to(b, 100.0)
        b.transfer_to(c, 50.0)
        assert a.balance == 200.0
        assert b.balance == 50.0
        assert c.balance == 50.0
 
    def test_should_allow_deposit_after_failed_withdrawal(self):
        account = BankAccount("Camila Ríos", initial_balance=50.0)
        with pytest.raises(InsufficientFundsError):
            account.withdraw(200.0)
        account.deposit(300.0)       # debe seguir funcionando con normalidad
        assert account.balance == 350.0
 
    def test_balance_should_be_read_only(self):
        account = BankAccount("Test User", initial_balance=100.0)
        with pytest.raises(AttributeError):
            account.balance = 9999.0  # no debe poder modificarse directamente
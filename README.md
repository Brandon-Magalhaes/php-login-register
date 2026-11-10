# Login e cadastro em PHP

Sistema simples de autenticação com **PHP + MySQL + sessões**: cadastro, login, página protegida, edição de dados e logout.

## Arquivos

| Arquivo | Função |
|---|---|
| `register.php` | cadastro de usuário |
| `index.php` | login |
| `home.php` | página protegida |
| `edit.php` | edição do perfil |
| `php/config.php` | conexão com o MySQL |
| `php/logout.php` | encerra a sessão |
| `sql/tutorial.sql` | script de criação do banco |

## Como rodar

1. Tenha PHP 8 e MySQL instalados.
2. Importe `sql/tutorial.sql`.
3. Ajuste as credenciais em `php/config.php`.
4. Suba o servidor:

```bash
php -S localhost:8000
```

## Limitações (importante)

Projeto de estudo, escrito sem preocupação de segurança:

- **A senha é gravada em texto puro** e comparada direto na consulta (`WHERE Email='$email' AND Password='$password'`). O correto é `password_hash()` / `password_verify()`.
- **SQL montado por interpolação de string** — vulnerável a SQL injection; faltam *prepared statements*.
- Não há validação de força de senha, recuperação de senha nem proteção CSRF.
- Não há testes.

Serve como registro do aprendizado de PHP/MySQL, não como base para produção.

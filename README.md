# auth-log-watch

Detector de brute-force e varredura em logs de autenticação.

> **Aviso etico:** ferramenta exclusiva para fins educacionais e testes em
> ambientes que voce possui ou tem autorizacao para auditar. Categoria:
> Defensiva. Nunca a use contra terceiros.

## Instalacao

```bash
git clone https://github.com/Diogo-Damasceno/auth-log-watch.git
cd auth-log-watch
python3 -m venv .venv && . .venv/bin/activate
pip install -e .
```

## Uso

Aponte para seus próprios logs para medir tentativas de intrusão.

Exemplos reais:

```
  $ auth-log-watch /var/log/auth.log
  ssh-brute: 142
  $ echo 'Failed password for root' | auth-log-watch
  ssh-brute: 1```

## Arquitetura

`src/auth_log_watch/core.py` tem a logica pura (funcoes testaveis); `cli.py` e a
casca de argumentos. Testes em `tests/` cobrem os casos principais.

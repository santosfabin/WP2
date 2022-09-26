# ****pw-inspector****

- A tool  to reduce the password list
- Command
    - Options:
        - -i
            - File to read passwords
        - -o
            - File to write valid passwords
        - -m
            - MINLEN
            - minimum length of valid password
        - -M
            - MAXLEN
            - maximum length  of valid password
        - -c
            - MINSETS
            - the minumum number of sets required (default: all given)
            - MINSETS o número mínimo de conjuntos necessários (padrão: todos dados)
    - Sets:
        - -l
            - lowcase characters (a, b, c, d, etc.)
        - -u
            - upcase characters (A,B,C,D, etc.)
        - -n
            - numbers (1,2,3,4, etc.)
        - -p
            - printable characters (which are not -l/-n/-p, e.g. $,!,/,(,*, etc.)
        - -s
            - special characters - all others not within the sets above

## Força bruta em ssh

- Command used

```bash
hydra -l msfadmin -P /usr/share/wordlists/rockyou.txt.gz 192.168.0.32 ssh -t 4 -V
```

- Explanation
    - hydra
        - programa de bruteforce usado
    - -l msfadmin
        - passando apenas um nome de usuário
        - é possível usar o comando -L e em seguida ser passado uma wordlist com nomes de usuários
    - -P /use/share/wordlist/rockyou.txt.gz
        - sendo o password seguindo do diretório da wordlist para ser usada
    - 192.168.0.32
        - IP da vítima
    - ssh
        - porta da vítima
    - -t 4
        - quantidade de threads que será usada
    - -V
        - verbose

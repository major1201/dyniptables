# dyniptables

Make iptables support domain expression, useful when you use DDNS

## Prerequisites

- iptables
- dig (bind-utils package on RHEL/CentOS)

## Usage

```
dyniptables [SUBCOMMAND] [OPTION]...

Subcommands:
    update              create or update the iptables rules
        update [Main Chain] [Sub-chain] [iptables option]...

    destroy             destroy iptables rules by custom chain
        destroy [Main Chain] [Sub-chain]

Domain expression:
    '{www.yourdomain.com}'
```

Examples

```bash
dyniptables update INPUT mychainname -s '{www.example.com}' -j ACCEPT
dyniptables destroy INPUT mychainname
```

## Remarks

- dyniptables creates DNS resolve cache in `/var/cache/dyniptables`
- cache older than 3 days would be cleared when you run the `dyniptables` command

## Skills

Put the dyniptables to `crontab` make you domain up-to-date.

## Contributing

Just fork the repositry and open a pull request with your changes.

## Licence

MIT

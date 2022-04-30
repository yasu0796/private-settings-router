# Private Settings for Router

## 0. Introduction

I switched my main internet line from PPPoE to IPoE because of the slow line speed.

However, in the case of IPoE, there are the following problems.

- Unable to open IPv4 tcp ports
- Less fixed DHCP on IPoE-enabled router

So, I create a router as a VM.

## 1. Install OS

Create VM like this.

```
          [ONU]
            |
     [Switching Hub]
        |        |
[IPoE router]    |
  | | |    |eth0 |eth1
[Clients] [Router VM]
```

Install OS by private cobbler with CentOS-8.1.1911-x86_64 profile.

## 2. Prepare

From here on out, I'm writing.

```bash
dnf install git ansible-core
git clone git@github.com:yasu0796/private-settings-router.git
```

if install ansible-core, need to install galaxy

```
ansible-galaxy collection install -r private-settings-router/requirements.yml
```

## 3. Run

```bash
cd private-settings-router
ansible-playbook -i hosts.yaml playbook.yaml --list-hosts
ansible-playbook -i hosts.yaml playbook.yaml --list-tasks
```

## Troubleshooting

## Limitations

## Information

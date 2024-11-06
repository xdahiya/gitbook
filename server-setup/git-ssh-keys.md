---
description: how to connect with the github using ssh keys
---

# Git ssh keys

## add ssh keys and push code to github



ssh-keygen -t ed25519 -C "[xdahiya@gmail.com](mailto:xdahiya@gmail.com)" -f \~/.ssh/key\_name

ssh-keygen -t ed25519 -C "[xdahiya@gmail.com](mailto:xdahiya@gmail.com)"

eval "$(ssh-agent -s)"

ssh-add \~/.ssh/id\_ed25519 or ssh-add \~/.ssh/key\_name

clip < \~/.ssh/id\_ed25519.pub

cat \~/.ssh/id\_ed25519.pub or cat \~/.ssh/key\_name.pub

ssh -T [git@github.com](mailto:git@github.com)

git remote remove origin git remote add origin [git@github.com](mailto:git@github.com):your\_username/your\_repository.git

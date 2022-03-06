# Useful Commands
Some personal useful commands, to make things easier.

## GitHub CLI Installation
```bash
curl -fsSL https://cli.github.com/packages/githubcli-archive-keyring.gpg | sudo dd of=/usr/share/keyrings/githubcli-archive-keyring.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" | sudo tee /etc/apt/sources.list.d/github-cli.list > /dev/null
sudo apt update
sudo apt install gh
```

## Gerrit Change-Id Git Hook
```bash
curl -Lo .git/hooks/commit-msg http://review.lineageos.org/tools/hooks/commit-msg
chmod u+x .git/hooks/commit-msg
```

## [Azure] Mount Disk to Linux VM
```bash
BLKNAME=sdX

sudo parted /dev/${BLKNAME} --script mklabel gpt mkpart ext4part ext4 0% 100%
sudo mkfs.ext4 /dev/${BLKNAME}1
sudo partprobe /dev/${BLKNAME}1

sudo mkdir /DATA
sudo mount /dev/${BLKNAME}1 /DATA
sudo chown -R $USER:$USER /DATA
```

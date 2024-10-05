
---

# My APT Repository

Welcome to **My APT Repository**! This repository contains `.deb` packages for installing software on Debian-based systems (like Ubuntu). You can easily add this repository to your APT sources and install packages from here.

## Adding the Repository

To add this APT repository to your system, follow these steps:

### Step 1: Add the APT Repository

First, add the repository to your APT sources list.

```bash
echo "deb [trusted=yes] https://github.com/koushalAkash26/mydeb-apt-repo/koushal-apt-repo stable main" | sudo tee /etc/apt/sources.list.d/myrepo.list
```

Alternatively, you can download the repository's `pgp-key.public` key file and add it to your trusted APT keys.

```bash
curl -fsSL https://github.com/koushalAkash26/my-apt-repo/raw/main/pgp-key.public | sudo gpg --dearmor -o /etc/apt/trusted.gpg.d/mykey.gpg

```

### Step 2: Update the Package List

Run the following command to update your local package list and retrieve information from the repository:

```bash
sudo apt-get update
```

### Step 3: Install Packages

Once you've added the repository, you can install packages from it. For example:

```bash
sudo apt-get install <package-name>
```

Replace `<package-name>` with the actual name of the package you want to install.

## Repository Structure

This repository follows a typical APT repository structure:

```plaintext
my-apt-repo/
├── dists/
│   └── stable/
│       └── main/
│           ├── binary-amd64/
│           │   └── Packages.gz
│           └── binary-i386/
│               └── Packages.gz
├── pool/
│   └── <package files here>
└── README.md
```

- **dists/**: Contains metadata and release information for the repository.
- **pool/**: Stores the actual `.deb` package files.
- **Packages.gz**: This file lists the available packages for a given architecture.
- **Release**: Contains information about the repository (like its version, codename, and architectures).

## Hosting on GitHub

This repository is hosted on [GitHub](https://github.com/koushalAkash26/my-apt-repo). You can browse the repository and find additional information there.

## License

This repository is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

---


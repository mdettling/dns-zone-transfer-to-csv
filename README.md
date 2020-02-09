# dns-zone-transfer-to-csv

*dns-zone-transfer-to-csv* is a small tool to dump DNS zones to CSV files. For
that the tool initiates a DNS zone transfer with the specified server and
writes the records received into a CVS file. It was written while doing a
migration of a larger DNS system hosting more than 2000 records. Of course such
migrations could also be done with BIND-style zone files but woking with
normalized, i.e. sorted CSV files proved to be more convenient and less error
prone. In the hope to be useful for others as well the tool is published here.

## Getting Started

The instructions below will help you to run *dns-zone-transfer-to-csv* on your
system.

### Prerequisites

First install the prerequisites needed to run *dns-zone-transfer-to-csv*:

```bash
# pip install dnspython
```

### Download Source Code

Download the source code of *dns-zone-transfer-to-csv*:

```bash
# git clone https://github.com/devsecurity-io/dns-zone-transfer-to-csv.git
```

### Usage

*dns-zone-transfer-to-csv* requires the server where to receive the zone
information from, the zone name and the name of the CSV file to write as
parameters. Example:

```bash
# python dns-zone-transfer-to-csv.py --server 1.2.3.4 --zone example.com --csv-file example-com.csv
```

## Known Limitations

- dns-zone-transfer-to-csv handles only the following DNS record types:
  - SOA
  - NS
  - CNAME
  - A
  - AAAA.

This was sufficient for my use case. See in the next section how you can
contribute to improve the tool.

## Contributing

Happy to receive your pull request. Updating this software especially makes
sense if you have faced the following error message:

``Record type not implemented.``

## Authors

- **Matthias Dettling**

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE)
file for details.
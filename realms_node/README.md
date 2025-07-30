# Downloading Realms data with note

## Why?

The best way to access Realms data is through their
[Realms JS SDK](https://www.npmjs.com/package/@solana/spl-governance). This
approach goes against the structure for the rest of the platforms, which is
broken down by platforms/organizations/proposals/votes.

## How?

1. First, get the list of ProgramIds from the realms homepage Next.js payload
```
GovER5Lthms3bLBqWub97yVrMmEogzX7xNjdXpPPCVZw    228
Ghope52FuF6HU3AAhJuAAyS2fiqbVhkAotb7YprL5tdS     10
hgovkRU6Ghe1Qoyb54HdSLdqN7VtxaifBzRmh9jtd3S       3
GqTPL6qRf5aUuqscLh8Rg2HTxPUXfhhAXDptTLhp1t2J      3
gUAedF544JeE6NYbQakQvribHykUNgaPJqcgf3UQVnY       2
5sGZEdn32y8nHax7TxEyoHuPS3UXfPWtisgm8kqxat8H      1
GMnke6kxYvqoAXgbFGnu84QzvNHoqqTnijWSXYYTFQbB      1
jdaoDN37BrVRvxuXSeyR7xE5Z9CAoQApexGrQJbnj6V       1
MGovW65tDhMMcpEmsegpsdgvzb6zUwGsNjhXFxRAnjd       1
A7kmu2kUcnQwAVn8B4znQmGJeUrsJ1WEhYVMtmiBLkEr      1
ALLGnZikNaJQeN4KCAbDjZRSzvSefUdeTpk18yfizZvT      1
GRNPT8MPw3LYY6RdjsgKeFji5kMiG1fSxnxDjDBu4s73      1
HT19EcD68zn7NoCF79b2ucQF8XaMdowyPt5ccS6g1PUx      1
GCockTxUjxuMdojHiABVZ5NKp6At8eTKDiizbPjiCo4m      1
GovMaiHfpVPw8BAM1mbdzgmSZYDw2tdP32J2fapoQoYs      1
smfjietFKFJ4Sbw1cqESBTpPhF4CwbMwN8kBEC1e5ui       1
AEauWRrpn9Cs6GXujzdp1YhMmv2288kBt3SdEcPYEerr      1
AVoAYTs36yB5izAaBkxRG67wL1AMwG3vo41hKtUSb8is      1
GMpXgTSJt2nJ7zjD1RwbT2QyPhKqD2MjAZuEaLsfPYLF      1
GmtpXy362L8cZfkRmTZMYunWVe8TyRjX5B7sodPZ63LJ      1
gSF1T5PdLc2EutzwAyeExvdW27ySDtFp88ri5Aymah6       1
5hAykmD4YGcQ7Am3N7nC9kyELq6CThAkU82nhNKDJiCy      1
JPGov2SBA6f7XSJF5R4Si5jEJekGiyrwP2m7gSEqLUs       1
J9uWvULFL47gtCPvgR3oN7W357iehn5WF2Vn9MJvcSxz      1
GovFUVGZWWwyoLq8rhnoVWknRFkhDSbQiSoREJ5LiZCV      1
GovHgfDPyQ1GwazJTDY2avSVY8GGcpmCapmmCsymRaGe      1
G41fmJzd29v7Qmdi8ZyTBBYa98ghh3cwHBTexqCG1PQJ      1
bqTjmeob6XTdfh12px2fZq4aJMpfSY1R1nHZ44VgVZD       1
```
2. Save this list to `program_ids.txt`
3. Download all deployments for each `programId` (many just have one) (n=2287)
4. Download all proposals for each deployment
5. Download all votes for each proposal
6. Format the data in python

## How? Using Docker

The `downloadvotes.Dockerfile` file is configured to use Docker to download
the votes.

This can be deployed to a server or a container service as this is a long-running
job.

Build and run the image with:

```
docker build -t downloadvotes -f downloadvotes.Dockerfile .
docker run -it downloadvotes
```

import argparse
import asyncio
import aiohttp
import dns.resolver

# Common subdomains wordlist
SUBDOMAIN_LIST = [
    "www", "mail", "ftp", "blog", "dev", "staging", "api", "test", "secure", "portal"
]

async def fetch_subdomain(session, domain, subdomain):
    full_url = f"{subdomain}.{domain}"
    try:
        dns.resolver.resolve(full_url, 'A')
        print(f"[+] Found: {full_url}")
        with open("output.txt", "a") as f:
            f.write(full_url + "\n")
    except dns.resolver.NXDOMAIN:
        pass
    except dns.resolver.NoAnswer:
        pass
    except dns.resolver.LifetimeTimeout:
        pass

async def enumerate_subdomains(domain):
    async with aiohttp.ClientSession() as session:
        tasks = [fetch_subdomain(session, domain, sub) for sub in SUBDOMAIN_LIST]
        await asyncio.gather(*tasks)

if __name__ == "__main__":
    parser = argparse.ArgumentParser(description="Automated Subdomain Enumeration Tool")
    parser.add_argument("domain", help="Target domain for enumeration")
    args = parser.parse_args()

    print(f"Starting subdomain enumeration for: {args.domain}\n")
    asyncio.run(enumerate_subdomains(args.domain))

# RepositoryPaolo
RepositeryEsame 
import requests
input_file = "input.txt"
output_file = "output.txt"
def shorten_url(url):
response = requests.get(f"https://is.gd/create.php?format=simple&url={url}")
return response.text.strip()
def process_urls():
with open(input_file, "r") as file:
urls = file.readlines()
with open(output_file, "w") as file:
for url in urls:
url = url.strip()
shortened_url = shorten_url(url)
file.write(f"{url}: {shortened_url}\n")

if __name__ == "__main__":
process_urls()


- 👋 Hi, I’m @Shr1mpSh4rk
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
Shr1mpSh4rk/Shr1mpSh4rk is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
import requests
from bs4 import BeautifulSoup

def crawl_webpage(url):
    response = requests.get(url)

    if response.status_code == 200:
        soup = BeautifulSoup(response.text, 'html.parser')

        title = soup.title.text
        paragraphs = soup.find_all('p')

        print(f'Title: {title}\n')

        for i, paragraph in enumerate(paragraphs, 1):
            print(f'Paragraph {i}: {paragraph.text}\n')
    else:
        print(f'Failed to retrieve the webpage. Status Code: {response.status_code}')

url_to_crawl = 'https://boo.vn/hang-moi/nam.html'
crawl_webpage(url_to_crawl)

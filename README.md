# Project-3-High-Throughput-Web-Crawler-solution

Download Here: [Project 3 – High Throughput Web Crawler solution](https://jarviscodinghub.com/assignment/project-3-high-throughput-web-crawler-solution/)

For Custom/Original Work email jarviscodinghub@gmail.com/whatsapp +1(541)423-7793

Overview
Content is king on the Internet today, and business thrive
or fail based on the value of content they collect, hoard,
and serve to their users. Protecting this data is difficult,
because the large majority of that content is available to
users, which means it is available to automated web
crawlers that mimic real users.
For this project, you will be implementing a parallel web
crawler that maximizes throughput when retrieving
content from a target website. This will be an adversarial
interaction, between the crawler will be trying to pull down
data from a server that is wary and prepared against
aggressive crawlers. The web server will have
implemented multiple layers of rate limits for incoming
network connections, which the crawler must overcome if
it wants to maximize its efficiency.
For this project, you will need learn how to interact with
HTTP servers (like how you interact with FTP servers in
Project 2). There are a set of interactions (again like
project 2) which your crawler (HTTP client) will need to
recognize/parse and respond).
You can start from https://en.wikipedia.org/wiki/
Hypertext_Transfer_Protocol which provides the list of the
commands.
There are three versions of the crawler that should be
implemented as part of this assignment.
1.[40%] Basic crawler. Your crawler will connect to the
target website, and fetch the main page. Once it
retrieves the main page (index.html), it will parse the
page and extract all links to objects and other pages,
put them on the crawler queue, and crawl them in turn,
repeating the process until all files and pages reachable
from index.html in a transitive closure. To identify itself
to the server, the crawler uses a single cookie with a
user ID.
2.[40%] Parallel flows vs. per-flow rate limits. The
server has per-flow rate limits that throttle any single
network connection to a max rate (R), and that puts a
ceiling on how fast the basic crawler can work. Version
2 of the crawler overcomes this limit by implementing
parallel connections with coordination. In this mode, the
crawler spawns multiple threads (like you guys did in
assignment 2), where each thread cooperates with the
others to speed up the download. Key difference is that
all threads share a single download queue, and any
parsed links to files or other pages gets put on the
same shared queue. Implemented correctly, N multiple
threads will ideally speed up the aggregate download
rate by roughly a factor of N, since each thread can
potentially max out throughput at R. Note that here, all
threads identify themselves to the server using the
same user cookie file.
3.[20%] Shared cookies vs. per-user rate limits. The
server is smarter than you thought, and also
implements a per-user rate limit, that limits the total
download rate by any number of connections by the
same user. This means that instead of getting N*R total
throughput with your N threads, you’re instead getting
some total throughput U, where U

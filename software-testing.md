# Software Testing


Intro
0:00
software testing. The part of software
0:02
development you skip in your personal
0:03
projects because you don't think it's
0:05
worth it. Yes, you. I'm talking to you.
0:07
You know yourself. But here's the thing.
0:09
Just because you skip it inside projects
0:11
doesn't mean it's optional in the real
0:12
world. Software testing isn't new. It's
0:15
been around almost as long as software
0:16
itself. But even with all the progress
0:18
in development tools and methodologies,
0:20
one thing hasn't changed. No software is
0:23
completely bug-free. Not Gmail, not VS
0:26
Code, or your favorite social media app.
0:27
And that's never going to change. Why?
0:30
Because at the end of the day, software
0:32
is written by people and people make
0:33
mistakes. Even the most experienced
0:35
engineers following the most rigorous
0:37
testing practices can miss edge cases or
0:39
face unexpected scenarios. The software
0:41
itself doesn't live in a vacuum either.
0:43
It evolves. It interacts with different
0:45
devices, operating systems, browsers,
0:47
and much more. Each one of those
0:49
variations introduces potential new
0:51
issues. And as we update, patch, or
0:53
expand the codebase, new bugs can sneak
0:55
in even when we fixed old ones. Some
0:57
bugs even lay dormant for years, hiding
1:00
in plain sight, waiting for the right
1:01
set of circumstances to appear. Take the
1:03
year 2000 problem or the Y2K bug. For
1:06
decades, developers stored years using
1:08
two digits, 78 for 1978, 99 for 1999 to
1:13
save memory. It worked just fine until
1:15
the year 2000 approached. When computers
1:17
read 00 as 1900 instead of 2000, it
1:20
created widespread concern that banking
1:22
systems, flight schedules, and
1:24
government records would fail. This bug
1:26
stayed hidden for years because no one
1:28
had ever tested dates outside the 1900
1:30
to 1999 range. It was a future proofing
1:32
failure and it highlights why we test.
1:34
Testing is how we manage risks. We can't
1:37
predict everything that will happen, but
1:38
we can try to protect against the most
1:40
likely and most dangerous failures. That
1:42
said, it's impossible to test every
1:44
single scenario. So, we use different
1:46
types of tests, each covering parts of
1:48
the system. And in this video, I'll be
1:50
going through some of the most popular
1:51
testing strategies used in software
1:53
development today. Let's get into it.
1:59
Software testing generally falls under
Functional Testing
2:01
two broad categories, functional and
2:04
non-functional testing. Let's start with
2:05
the first, functional testing.
2:07
Functional testing checks that the
2:09
software behaves the way it's supposed
2:10
to. It's about making sure inputs
2:12
produce the right outputs and that
2:14
features work according to the
2:15
requirement. Let's say we're building a
2:17
file sharing approval app for a team.
2:19
Users should be able to log in, upload
2:21
documents, trigger an approval workflow,
2:23
and eventually archive the file.
2:25
Functional testing would verify that
2:27
users can login with the valid
2:28
credentials, upload files, preview them,
2:31
kick off approvals, and archive the
2:33
document when they're done. Each step is
2:35
validated to make sure it does what it's
2:36
supposed to do. Now, let's look at some
2:38
type of functional testing. The first is
2:40
unit test. Unit test are the foundation.
2:43
They focus on the smallest piece of
2:44
code, individual functions, methods, or
2:47
modules, and verify that they work in
2:49
isolation. For example, you might have a
2:51
function like this that checks whether a
2:53
document upload is valid. The function
2:55
checks the file name, file extension,
2:56
and the file size. A unit test for the
2:59
function might look something like this,
3:00
where we check various combinations of
3:02
the file name, and sizes to confirm the
3:04
logic is correct and working how we
3:05
expect it to. Unit tests are written by
3:07
developers during development. They
3:10
allow bugs to be caught early and make
3:11
it easier to debug issues since failures
3:14
are scoped to just a specific piece of
3:15
code. But not everything should be unit
3:18
tested. A common mistake is writing unit
3:20
tests that incorporate external systems
3:21
like API calls, databases, or file
3:24
storage. This is an antiattern because
3:26
those systems can introduce flaky tests.
3:28
Tests that can sometimes pass or
3:30
sometimes fail often due to things
3:32
outside your control like network
3:33
instability or service downtime. To
3:35
avoid this, we use mocking. Mock
3:37
simulate the behavior of external
3:39
systems so you can focus on the logic in
3:41
your code. Instead of connecting to a
3:43
real database to test login logic, you
3:45
can mock a database call to return a
3:47
valid user or an error and test how your
3:49
code responds. Now once the individual
3:51
units work, the next step is to make
3:53
sure they work together and that's where
3:54
integration testing comes in. It checks
3:57
that components interact correctly. For
3:59
our file sharing app, we might write
4:00
integration tests to verify that after
4:02
uploading a file, the system kicks off
4:04
an approval workflow and logs the event
4:06
in the activity log. Some integration
System Testing
4:08
tests can also include interactions with
4:10
external systems like calling thirdparty
4:12
APIs and making sure the response is
4:14
processed correctly. It's all about
4:16
making sure the seams between the parts
4:18
of your systems work correctly. The next
4:20
series of tests are called systems test.
4:22
Here we step up a level and test the
4:24
application as a whole. System testing
4:26
ensures that the complete integrated
4:28
software meets all the functional
4:29
requirements for our file sharing app.
4:32
This can include everything from login
4:33
to file upload and archiving all tested
4:36
in one big flow. System testing often
4:38
involves several types of tests. One of
4:40
them is end toend tests. End toend test
4:42
simulates the complete user journey. For
4:44
example, a test might start by logging
4:46
in, uploading a file, assigning it for
4:49
approval, waiting for the response, and
4:50
then archiving it. If it all passes,
4:53
then everything looks good. It's a
4:54
realistic walkthrough that mimics how a
4:56
real user would interact with the
4:58
application. Another type of system test
5:00
is the smoke test. Smoke tests are quick
5:02
tests to make sure that the core
5:03
features work after a new deployment or
5:05
a major code change. Say we just
5:07
deployed a new version of our app. A
5:09
smoke test might check does the app
5:10
load. Can I login? Can I upload a file?
5:13
If any of these things fail, then
5:15
there's no point in running deeper tests
5:16
yet. We need to fix the basics. Next,
5:19
there's acceptance testing and user
5:21
acceptance testing. Acceptance testing
5:23
checks whether the system meets the
5:24
business requirements and it's ready for
5:26
release. The quality assurance team or
5:28
the business stakeholders typically do
5:30
this test. User acceptance test usually
5:32
takes this further by putting the
5:34
software in the hands of the actual
5:35
users to see if it meets their real
5:37
world workflows. Now functional testing
NonFunctional Testing
5:39
is all about asking one question. Does
5:41
this thing work properly? But just
5:43
because something works doesn't mean it
5:45
works well. That's where the second
5:47
category of testing comes in.
5:48
Non-functional testing. Non-functional
5:51
testing focuses on how the system
5:52
performs, not just whether it functions.
5:54
It covers things like performance,
5:56
security, usability, scalability, and
5:59
much more. One example of non-functional
6:01
testing is load testing. It evaluates
6:03
how a system performs under pressure.
6:05
Say our file sharing system is expected
6:07
to handle 10,000 concurrent uploads.
6:10
Load testing simulates that volume to
6:12
see if the system can hold up or if it
6:14
crashes. Tools like JMeter or Gatling
6:16
can help simulate traffic that can help
6:18
us answer questions like how fast can
6:20
files be uploaded during peak hours?
6:22
When does the system start slowing down?
6:24
How many users can be logged in at once
6:26
before performance start to tank?
6:28
Another example of non-functional
6:30
testing is security tests. It checks for
6:32
vulnerabilities. Things like injection
Security Testing
6:34
attacks, unauthorized access, or data
6:36
leakage. For example, you'd want to test
6:38
whether users can access documents they
6:40
don't own or if someone can bypass
6:42
authentication using forged tokens. Some
6:44
techniques for security testing include
6:46
penetration testing, trying to break
6:48
into the system, static code analysis,
6:50
finding weak spots in the code, and risk
6:52
assessment, understanding potential
6:54
threats. So to recap, software testing
6:57
should always start with unit tests to
6:58
verify the code in small chunks. Then we
7:01
move to integration testing to make sure
7:02
those bigger modules work perfectly fine
7:04
together. Next, we run systems test
7:06
including end-to-end test and smoke test
7:08
to verify everything works as a whole.
7:10
Then comes acceptance test where we
7:12
validate business goals and users needs.
7:14
Finally, we run non-functional tests
7:16
like loaded and security testing to
7:18
ensure the system performs well and
7:20
stays safe. Early on, tools like JUnit
7:23
and Mochito can help with unit test and
7:24
integration test. Later on, tools like
7:27
Selenium make end to-end test and user
7:29
acceptance testing easier to manage.
7:31
Now, of course, there are many more
7:32
types of tests. There's regression test,
7:34
API test, blackbox test, white blood
7:37
test, and much more. But they're all
7:39
forms of system test and support the
7:40
same goal, making the software better.
7:43
Choosing the right tools at the right
7:44
time will help make your testing more
7:46
effective and less painful. At the end
7:48
of the day, tests are your safety net.
7:50
They give you confidence that your code
7:51
works as expected and that future
7:53
changes won't break things quietly. If
7:55
you found this video helpful, don't
7:57
forget to give it a thumbs up and
7:58
subscribe for more videos like this. And
8:00
if you want to hear more about the world
8:01
of software engineering beyond writing
8:03
code, check out Beyond the Build podcast
8:05
hosted by me and my good friend. We talk
8:07
about everything that makes this field
8:08
what it is, from soft skills to career
8:10
growth and everything in between. Thanks
8:12
for watching and I'll see you on the
8:14
next one. is


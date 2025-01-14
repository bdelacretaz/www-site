Title: ASF Project Security for Committers
license: https://www.apache.org/licenses/LICENSE-2.0

# Introduction #

This section is intended to provide guidance to Apache committers on how
security vulnerabilities should be handled. The [Apache Security
Team](mailto:security@apache.org) is available to provide help and advice
to Apache projects should it be required.

# Publishing information #

Projects with known, published vulnerabilities should provide information
about those vulnerabilities as part of the project web pages e.g. the
[httpd security pages](http://httpd.apache.org/security_report.html). The
security information should be clearly linked from the project's homepage.

Security vulnerabilities should not be entered in a project's public bug
tracker unless the necessary configuration is in place to limit access to
the issue to only the reporter and the project team.

# Project specific security mailing lists #

Projects may also wish to create a project specific security mailing list.
These take the form of security@project.apache.org, e.g.
security@tomcat.apache.org

When the infrastructure team creates these lists, they are configured so that
all messages are automatically copied to security@apache.org. If is not,
therefore, necessary to cc security@apache.org when sending mail to a project
specific security mailing list.

It is expected that a subset of project PMC members and committers will be
subscribed to the project specific security mailing list. They are not intended
to be used as a third-party notification system and non-committers should not
be subscribed to the lists.

# Vulnerability handling #

A typical process for handling a new security vulnerability is as follows.
Projects that wish to use other processes MAY do so, but MUST clearly and
publicly document their process and have security@ review it ahead of time.

<b><i>Note: this process changed in February 2021 when an internal portal
for CVE allocation and submission was introduced</i></b>

<b><i>Note: No information should be made public about the vulnerability until it is
formally announced at the end of this process. That means, for example that a Jira
issue must NOT be created to track the issue since that will make the issue public.
Also the messages associated with any commits should not make ANY reference to the
security nature of the commit.</i></b>

1. The person discovering the issue, the reporter, reports the
vulnerability privately to security@<i>project</i>.apache.org or to
security@apache.org

1. Messages that do not relate to the reporting or managing of an
undisclosed security vulnerability in Apache software are ignored and no
further action is required.

1. If reported to security@apache.org, the security team will forward
the report to the project's security list or, of the project does not
have a security list, to the project's private (PMC) mailing list.
The security team will respond to the original reporter that this has
been done.

1. The project team sends an e-mail to the original reporter to acknowledge the report.
This e-mail must be cc'd to security@<i>project</i>.apache.org if it exists, or
security@apache.org otherwise.

1. The project team investigates report and either rejects it or accepts
it.

1. If the report is rejected, the project team writes to the reporter to
explain why.    This e-mail must be cc'd to security@<i>project</i>.apache.org if it exists, or
security@apache.org otherwise.

1. If the report is accepted, the project team writes to the reporter to let them
know it is accepted and that they are working on a fix.

1. The project team requests a CVE name from security@apache.org by
sending an e-mail with the subject "CVE request for..." and providing a
short (one line) description of the vulnerability. security@apache.org can
help determine if a report requires multiple CVEs or if multiple reports
should be merged under a single CVE.

1. The ASF security team will allocate a CVE and send a link to the
internal portal, https://cveprocess.apache.org, where details of the
vulnerability can be entered.

1. The project team agrees the fix on their private list.

1. The project team write up the details of the vulnerability on the
internal portal.  The portal generates draft announcement texts.  For
an example of an announcement see [Tomcat's announcement of
CVE-2008-2370](http://markmail.org/message/w7mdjdxeqius7d6l). The
level of detail to include in the report is a matter of
judgement. Generally, reports should contain enough information to
enable people to assess the risk associated with the vulnerability for
their system and no more. Steps to reproduce the vulnerability are not
normally included.

1. The project team provides the reporter with a copy of the fix and a
draft vulnerability announcement for comment.

1. The project team agrees the fix, the announcement and the release
schedule with the reporter.

1. The project team commits the fix. No reference should be made to the
commit being related to a security vulnerability.

1. The project team creates a release that includes the fix.

1. The project team announces the vulnerability. The vulnerability
announcement should be sent after, or at the same time as, the release announcement to the
following destinations.  The internal portal generates texts that can be used for
the emails.

    a. the same destinations as the release announcement

    b. the vulnerability reporter

    c. the project's security list (or security@apache.org if the project does
not have a dedicated security list)

    d. oss-security@lists.openwall.com ([subscription not required](http://oss-security.openwall.org/wiki/mailing-lists)).

    e. The project's security pages should also be updated.

    f. Set the status of the vulerability to 'READY' in the internal portal, this notifies the
    security team who will then submit the information to the CVE project.

    This is the first point that any information regarding the vulnerability is made public.

1. The log for the svn commit that applied the fix is updated to include
the CVE number. Projects that use git as their primary source code control
system should not do this as editing a pushed commit causes all sorts of
problems.

If the project does not have a dedicated security@project.apache.org
mailing list, all communication regarding the vulnerability should be
copied to security@apache.org. There is no need to do this for messages
sent to security@project.apache.org since these are automatically copied to
security@apache.org.

Information may be shared with domain experts (eg colleagues at your
employer) at the discretion of the project's security team providing that
it is made clear that the information is not for public disclosure and that
security@apache.org or the project's security mailing list must be copied
on any communication regarding the vulnerability.

# CVE names #

[Common Vulnerabilities and Exposures](https://cve.mitre.org/) (CVE)
IDs are a unique identifiers given to security flaws.  The Apache
Security Team is a <a href="https://cve.mitre.org/cve/cna.html">CVE Numbering Authority (CNA)</a> covering all Apache projects and is the only
group able to allocate names to Apache Software Foundation project issues.

If you believe Mitre have the details of an issue described
incorrectly, see the [CVE
FAQ](https://cve.mitre.org/about/faqs.html#b12) for how to contact
them with corrections.


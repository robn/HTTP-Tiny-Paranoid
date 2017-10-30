# NAME

HTTP::Tiny::Paranoid - A safer HTTP::Tiny

# SYNOPSIS

    # use just like HTTP::Tiny
    use HTTP::Tiny::Paranoid;
    my $response = HTTP::Tiny::Paranoid->new->get('http://example.com');

    # block or whitelist specific hosts
    # delegates to Net::DNS::Paranoid
    HTTP::Tiny::Paranoid->blocked_hosts([...]);
    HTTP::Tiny::Paranoid->whitelisted_hosts([...]);

# DESCRIPTION

This module is a subclass of HTTP::Tiny that performs exactly one additional
function: before connecting, it passes the hostname to
[Net::DNS::Paranoid](https://metacpan.org/pod/Net::DNS::Paranoid). If the hostname is rejected, then the request
is aborted before a connect is even attempted.

By default, [Net::DNS::Paranoid](https://metacpan.org/pod/Net::DNS::Paranoid) rejects connections to private network
ranges. The blocklist & whitelist can be manipulated using the `blocked_hosts`
and `whitelisted_hosts` class methods.

# SEE ALSO

- [HTTP::Tiny](https://metacpan.org/pod/HTTP::Tiny)
- [Net::DNS::Paranoid](https://metacpan.org/pod/Net::DNS::Paranoid)
- [LWPx::ParanoidAgent](https://metacpan.org/pod/LWPx::ParanoidAgent)
- [LWP::UserAgent::Paranoid](https://metacpan.org/pod/LWP::UserAgent::Paranoid)

# SUPPORT

## Bugs / Feature Requests

Please report any bugs or feature requests through the issue tracker
at [https://github.com/robn/HTTP-Tiny-Paranoid/issues](https://github.com/robn/HTTP-Tiny-Paranoid/issues).
You will be notified automatically of any progress on your issue.

## Source Code

This is open source software. The code repository is available for
public review and contribution under the terms of the license.

[https://github.com/robn/HTTP-Tiny-Paranoid](https://github.com/robn/HTTP-Tiny-Paranoid)

    git clone https://github.com/robn/HTTP-Tiny-Paranoid.git

# AUTHORS

- Robert Norris <rob@eatenbyagrue.org>

# COPYRIGHT AND LICENSE

This software is copyright (c) 2014 by Robert Norris.

This is free software; you can redistribute it and/or modify it under
the same terms as the Perl 5 programming language system itself.

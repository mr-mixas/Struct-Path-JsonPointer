# NAME

Struct::Path::JsonPointer - JsonPointer ([rfc6901](https://tools.ietf.org/html/rfc6901))
syntax frontend for [Struct::Path](https://metacpan.org/pod/Struct::Path)

<a href="https://travis-ci.org/mr-mixas/Struct-Path-JsonPointer.pm"><img src="https://travis-ci.org/mr-mixas/Struct-Path-JsonPointer.pm.svg?branch=master" alt="Travis CI"></a>
<a href='https://coveralls.io/github/mr-mixas/Struct-Path-JsonPointer.pm?branch=master'><img src='https://coveralls.io/repos/github/mr-mixas/Struct-Path-JsonPointer.pm/badge.svg?branch=master' alt='Coverage Status'/></a>
<a href="https://badge.fury.io/pl/Struct-Path-JsonPointer"><img src="https://badge.fury.io/pl/Struct-Path-JsonPointer.svg" alt="CPAN version"></a>

# VERSION

Version 0.02

# SYNOPSIS

    use Struct::Path qw(path);
    use Struct::Path::JsonPointer qw(str2path);

    my $data = {
        "foo"   => ["bar", "baz"],
        ""      => 0,
        "a/b"   => 1,
        "c%d"   => 2,
        "e^f"   => 3,
        "g|h"   => 4,
        "i\\j"  => 5,
        "k\"l"  => 6,
        " "     => 7,
        "m~n"   => 8
    };

    my ($found) = path($data, str2path('/foo/0'), deref => 1);
    print $found; # 'bar'

# EXPORT

Nothing is exported by default.

# SUBROUTINES

## path2str

Convert [Struct::Path](https://metacpan.org/pod/Struct::Path) path to JsonPointer.

    $pointer = path2str($path);

## str2path

Convert JsonPointer to [Struct::Path](https://metacpan.org/pod/Struct::Path) path.

    $path = str2path($pointer);

# AUTHOR

Michael Samoglyadov, `<mixas at cpan.org>`

# BUGS

Please report any bugs or feature requests to
`bug-struct-path-jsonpointer at rt.cpan.org`, or through the web interface at
[http://rt.cpan.org/NoAuth/ReportBug.html?Queue=Struct-Path-JsonPointer](http://rt.cpan.org/NoAuth/ReportBug.html?Queue=Struct-Path-JsonPointer). I
will be notified, and then you'll automatically be notified of progress on your
bug as I make changes.

# SUPPORT

You can find documentation for this module with the perldoc command.

    perldoc Struct::Path::JsonPointer

You can also look for information at:

- RT: CPAN's request tracker (report bugs here)

    [http://rt.cpan.org/NoAuth/Bugs.html?Dist=Struct-Path-JsonPointer](http://rt.cpan.org/NoAuth/Bugs.html?Dist=Struct-Path-JsonPointer)

- AnnoCPAN: Annotated CPAN documentation

    [http://annocpan.org/dist/Struct-Path-JsonPointer](http://annocpan.org/dist/Struct-Path-JsonPointer)

- CPAN Ratings

    [http://cpanratings.perl.org/d/Struct-Path-JsonPointer](http://cpanratings.perl.org/d/Struct-Path-JsonPointer)

- Search CPAN

    [http://search.cpan.org/dist/Struct-Path-JsonPointer/](http://search.cpan.org/dist/Struct-Path-JsonPointer/)

# SEE ALSO

[JSON::Pointer](https://metacpan.org/pod/JSON::Pointer), [rfc6901](https://tools.ietf.org/html/rfc6901)

[Struct::Path](https://metacpan.org/pod/Struct::Path), [Struct::Path::PerlStyle](https://metacpan.org/pod/Struct::Path::PerlStyle), [Struct::Diff](https://metacpan.org/pod/Struct::Diff)

# LICENSE AND COPYRIGHT

Copyright 2018 Michael Samoglyadov.

This program is free software; you can redistribute it and/or modify it under
the terms of either: the GNU General Public License as published by the Free
Software Foundation; or the Artistic License.

See [http://dev.perl.org/licenses/](http://dev.perl.org/licenses/) for more information.

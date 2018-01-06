# NAME

Struct::Path::JsonPointer - JsonPointer ([rfc6901](https://tools.ietf.org/html/rfc6901))
frontend for [Struct::Path](https://metacpan.org/pod/Struct::Path).

# VERSION

Version 0.01

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

Convert [Struct::Path](https://metacpan.org/pod/Struct::Path) path to JsonPointer path.

    $jp_path = path2str($sp_path);

## str2path

Convert JsonPointer path to [Struct::Path](https://metacpan.org/pod/Struct::Path) path.

    $sp_path = str2path($jp_path);

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

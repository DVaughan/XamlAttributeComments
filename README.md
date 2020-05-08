# XamlAttributeComments
A small example of how to comment out individual attributes in XAML.

XML doesn't support commenting out attributes.
If you're working with XAML and you wish to comment out an attribute, it usually involves cutting and pasting. 
Here's an alternative that uses the Ignorable attribute to hide attributes from the XAML parser.

First, add a new xmlns definition to the root element in your XAML file.

```
<Window x:Class="XamlAttributeComments.MainWindow"
        ...
        xmlns:c="http://example.com"
```

Then add the namespace alias to the Ignorable attribute, like so:

```
<Window x:Class="XamlAttributeComments.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:c="http://example.com"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        mc:Ignorable="d c"
```

Now you can comment out attributes by prefixing them with c:, like so:

```
<TextBlock Text="Some Text" c:HorizontalAlignment="Center" />
```

That's it! A simple way to comment out XAML attributes.


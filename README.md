# node-gettext

**node-gettext** is a Node.JS module to use .MO files.

## Support node-gettext development

## Installation

    npm install node-gettext

## Usage

### Create a new Gettext object

    var Gettext = require("node-gettext");

    var gt = new Gettext();
    
### Add a language - addTextdomain(domain, file)

Language data needs to be file contents in the Buffer format

*addTextdomain(domain, file_contents)*

    var file_contents = fs.readFileSync("et.mo");
    gt.addTextdomain("et", file_contents);

### Change default language - textdomain(domain)

*textdomain(domain)*

    gt.textdomain("et");

### Load a string from default language file

*gettext(msgid)*

    var greeting = gt.gettext("Hello!");
    
### Load a string from a specific language file

*dgettext(domain, msgid)*

    var greeting = gt.dgettext("et", "Hello!");
    
### Load a plural string from default language file

*ngettext(msgid, msgid_plural, count)*

    gt.ngettext("%d Comment", "%d Comments", 10);

### Load a plural string from a specific language file

*dngettext(domain, msgid, msgid_plural, count)*

    gt.dngettext("et", "%d Comment", "%d Comments", 10)
    
### Load a string of a specific context

*pgettext(msgctxt, msgid)*

    gt.pgettext("menu items", "File");

### Load a string of a specific context from specific language file

*dpgettext(domain, msgctxt, msgid)*

    gt.dpgettext("et", "menu items", "File");
    
### Load a plural string of a specific context

*npgettext(msgctxt, msgid, msgid_plural, count)*

    gt.npgettext("menu items", "%d Recent File", "%d Recent Files", 3);
    
### Load a plural string of a specific context from specific language file

*dnpgettext(domain, msgctxt, msgid, msgid_plural, count)*

    gt.dnpgettext("et", "menu items", "%d Recent File", "%d Recent Files", 3);

## License

MIT
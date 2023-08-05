<!-- [![Code style: yapf pep8](./figs/code_style_yapf.svg)](https://github.com/google/yapf) -->

# Physics and Coding Synergy 

`Physics` and `Coding` are two interconnected fields that often complement each other, particularly in scientific and technological advancements. Coding empowers physicists to tackle complex problems, analyze data, develop simulations, and advance our understanding of the physical world. The combination of physics and coding enables groundbreaking research, technological innovations, and the development of new scientific methodologies.

To fully exploit physics and coding synergy, we're going to have a monthly meeting schedule:

1. Approximately once a month, the specific meeting time will be confirmed three days in advance.
2. The focus of the meetings will be on programming as a tool to solve specific research-related problems: Programming is likened to a shovel, while research is the gold mine.
3. In the first six months, the meetings will primarily cover the fundamentals of physics as the gold mine, teaching participants to use tools like `python` as shovels. After six months, we will progress to using advanced shovels: `python` + `artificial intelligence (AI)`.

![Physics and Coding Synergy: Here we use a picture of fractal to imply such ethereal synergy.](./figs/fractal.jpg "Physics and coding synergy")

## Documents

In the folder and its subfolders, there will be various file formats, such as `md`, `py`, `ipynb`, and `pdf` files. Our reading order should be `md` files first, followed by `ipynb` or `py` files. (Here all `md` files are named as `README`.) We typically edit the first three file types, while `pdf` files are generated from `md` or `ipynb` files. 
To ensure smooth generation of PDF files, you need to install the following software or libraries beforehand:

1. [Pandoc, rsvg-convert (Windows), librsvg (MacOS)](https://pandoc.org/installing.html)
2. [Tex Live](https://tug.org/texlive/)
3. [Jupyter Notebook](https://jupyter.org/install)

### Markdown to PDF 

After you finish your markdown file, you can use the following command to convert it to a pdf file:

```bash
pandoc --pdf-engine=xelatex -s -V geometry:margin=1.05in --highlight-style breezedark 
    [inputfilename].md -o [outputfilename].pdf
```

### Jupyter Notebook to PDF

```bash
jupyter nbconvert --to pdf [inputfilename].ipynb --output [outputfilename].pdf
```
During the conversion process from `ipynb` to `pdf`, you will notice that a default title is generated. If you wish to customize the title and author, please follow the instructions below:

*In the directory containing the ipynb file, execute the command `jupyter notebook`. Your default browser will open the directory. Open the ipynb file, then go to Edit $\rightarrow$ Edit Notebook Metadata. In the opened `JSON` file, input the following:*
```json
{
  "authors": [
    {
      "name": "your name"
    }
  ],
  "title": "your title"
}
```
And then do the conversion again.


## Journey

<a href="./001_development-environment/README.md" alt="Please see the link for details">&#x1F517; 001. Development environment (06-23-2023)</a>

<a href="./002_energy-bands/README.md" alt="Please see the link for details">&#x1F517; 002. Energy bands (07-30-2023)</a>
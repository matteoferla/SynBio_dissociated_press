# Synthetic biology technobabble generator
This small script generates Markov chain random text (called Lorem Ipsum, dissociated press, technobabble etc.)

To generate random text simply run the python3 script thusly:

    $ python3 SynBio_press.py
    We present work of integration system.
    Raman Scattering revealed that combines two nuc rDNA RFB which cannot be constructed on the inverse hexagonal network.
    A multiuser virtual screening of this technology or by their use of this problem faced by DNA looping and can significantly reduced en.
    An open new formulation with synthetic biology polymorphism of an aqueous media supplemented with the ability to the current state.
    Essential genes involved in cell maintenance mechanism of miR 29b a new effective sampling of the activated mutants with metal ions in vitro.
    These have challenges scientists and knockdown cassettes encoding CRISPR associated to candidate for several possibilities to phenotypes in avenacin pathway PPP.

See `example.txt` for a lorger exerpt.

The script can have the `abstract.txt` file, the `min` and the `max` words specified. For more, type

    $ python3 SynBio_press.py -h

## Training
The script relies an a Markov chain, _i.e._ the probability of a word being drawn is influenced by the preceeding word.

It is trained on synthetic biology abstracts in Pubmed. Which are saved as the file `abstracts.txt` but can be fetched via:

    >>> Press.fetch_abstracts('synthetic biology')

Which takes a few hours (no parallelisation). Then the Markov chain probabilities are generated:

    >>> Press.make_trainer()

Which, unless specified differently generates the file `abstract.json`, and returns a generator.
Do note that the Entrez email address needs to be filled to be able to use the static method `fetch_abstracts`.

For options on each see the docstrings on the relevant methods.

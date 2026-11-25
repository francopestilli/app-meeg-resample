# Resample MEEG file

<!-- brainlife-app:begin (generated from the App manifest; edit the manifest, not this block) -->

> **Resamples all channels of an MNE raw MEG/EEG file to a new sampling rate with MNE-Python raw.resample and saves the result.**

Calls raw.resample with the chosen sampling frequency, padding and window; stim channels are subsampled without filtering. Use it to reduce data size or match sampling rates before further processing.

| | |
|---|---|
| 📥 **Inputs** | `neuro/meeg/mne/raw` |
| 📤 **Outputs** | `neuro/meeg/mne/raw` |
| 🐳 **Container** | `brainlife/mne:0.23dev` |
| ⚙️ **Resources** | 8 CPUs |
| 🔗 **Run it** | [doi.org/10.25663/brainlife.app.781](https://doi.org/10.25663/brainlife.app.781) |

#### 📥 Inputs

| Input | Datatype | Required | Description |
|---|---|---|---|
| `raw01` | `neuro/meeg/mne/raw` | yes | Continuous MEG/EEG data (MNE raw). |

#### 📤 Outputs

| Output | Datatype | Description |
|---|---|---|
| `out_dir` | `neuro/meeg/mne/raw` | Resampled raw data (raw.fif). |

<details>
<summary><b>⚙️ Parameters</b> (6)</summary>

| Parameter | Type | Default | Description |
|---|---|---|---|
| `sfreq` | number | `1` | New sample rate to use. |
| `npad` | number | `100` | Amount to pad the start and end of the data. Can also be “auto” to use a padding that will result in a power-of-two size (can be much faster). |
| `window` | string | `boxcar` | Frequency-domain window to use in resampling. See scipy.signal.resample(). |
| `pad` | string | `reflect_limited` | The type of padding to use. Supports all numpy.pad() mode options. Can also be "reflect_limited", which pads with a reflected version of each vector mirrored on the first and last values of the vector, followed by zeros. The default is 'reflect_limited'. |
| `stim_picks` | string | `None` | Stim channels. These channels are simply subsampled or supersampled (without applying any filtering). This reduces resampling artifacts in stim channels, but may lead to missing triggers. If None, stim channels are automatically chosen using mne.pick_types(). |
| `events` | string | `None` | An optional event matrix. When specified, the onsets of the events are resampled jointly with the data. NB: The input events are not modified, but a new array is returned with the raw instead. |

</details>

📚 **References used by this App:**
- Hayashi S, Caron BA, et al., Pestilli F. brainlife.io: A decentralized and open source cloud platform to support neuroscience research. arXiv (2023).
- Gramfort A, et al. MEG and EEG data analysis with MNE-Python. Front Neurosci 7:267 (2013). [doi:10.3389/fnins.2013.00267](https://doi.org/10.3389/fnins.2013.00267)

<!-- brainlife-app:end -->

[![Abcdspec-compliant](https://img.shields.io/badge/ABCD_Spec-v1.1-green.svg)](https://github.com/brain-life/abcd-spec)
[![Run on Brainlife.io](https://img.shields.io/badge/Brainlife-bl.app.781-blue.svg)](https://doi.org/10.25663/brainlife.app.781)


## Documentation
This Brainlife App resamples all channels of a M/EEG MNE fif file.


## Authors
- [Guiomar Niso](guiomar.niso@ctb.upm.es), Instituto Cajal, CSIC, Spain

## Citations
We kindly ask that you cite the following articles when publishing papers and code using this app. 

1. **brainlife. io: A decentralized and open source cloud platform to support neuroscience research**. Hayashi, S., Caron, B. A., et al. & Pestilli, F. (2023). ArXiv. https://www.ncbi.nlm.nih.gov/pmc/articles/PMC10274934/

2. **MEG and EEG data analysis with MNE-Python**. Gramfort A, et al. & Hämäläinen MS. (2013). Frontiers in Neuroscience, 7(267):1–13, 2013. https://doi.org/10.3389/fnins.2013.00267

## Funding Acknowledgement
brainlife.io is publicly funded and for the sustainability of the project we kindly ask that you acknowledge the following funding sources:

[![NSF-BCS-1734853](https://img.shields.io/badge/NSF_BCS-1734853-blue.svg)](https://nsf.gov/awardsearch/showAward?AWD_ID=1734853)
[![NSF-BCS-1636893](https://img.shields.io/badge/NSF_BCS-1636893-blue.svg)](https://nsf.gov/awardsearch/showAward?AWD_ID=1636893)
[![NSF-ACI-1916518](https://img.shields.io/badge/NSF_ACI-1916518-blue.svg)](https://nsf.gov/awardsearch/showAward?AWD_ID=1916518)
[![NSF-IIS-1912270](https://img.shields.io/badge/NSF_IIS-1912270-blue.svg)](https://nsf.gov/awardsearch/showAward?AWD_ID=1912270)
[![NIH-NIBIB-R01EB030896](https://img.shields.io/badge/NIH_NIBIB-R01EB030896-green.svg)](https://grantome.com/grant/NIH/R01-EB030896-01)


#### MIT Copyright (c) 2021 brainlife.io The University of Texas at Austin and Indiana University

# Detecting and Understanding Mobile Proxy Networks
This site provides data and code related to our research on mobile proxy networks.
Please cite the following paper when using our data or code in your research :smile: .
```bibtex
@inproceedings{mi2021your,
  title={Your Phone is My Proxy: Detecting and Understanding Mobile Proxy Networks},
  author={Mi, Xianghang and Tang, Siyuan and Li, Zhengyi and Liao, Xiaojing, and Qian, Feng and Wang, Xiaofeng},
  booktitle={NDSS},
  year={2021}
}
```

**We are working hard to prepare datasets for release and the timeline is as below**.
| Category      | Planned Release Date|
| ------------- |:-------------:|
| Research Dataset| Dec 2020 |
| Research Code     | Feb 2021    |

Free free to contact [the corresponding author through email](mailto:xianghangmi@gmail.com) for any questions.

## Datasets
| Name      | Description|Download|
| ------------- |:-------------:|:-------------:|
| Proxy IPs| 8-million proxy IPs as captured in our infiltration |[link](https://drive.google.com/file/d/1NBwytQCK0j0BQAbiVD90qkiir8cbOl5l/view?usp=sharing)|
| Proxy SDK Signatures     | The signatures of mobile proxy SDK, either high confidence or low confidence     |[link](/datasets/signatures/)|
| Android APKs (proxy programs) | hash values as well as metadata of Android APKs serving as proxy programs | [link](/datasets/final_proxy_apks.json)| 

**Proxy IPs**. As shown in the above table, each row in the released file is a proxy IP. If you are interested in more metadata such as timestamps when capturing proxy IPs as well as proxy providers to which a proxy IP belongs, please contact the corresponding author as denoted above.

**Proxy SDK Signatures**.
SDK signature are grouped by proxy providers in separate signature files as listed in *datasets/signatures*.
Each signature consists of several space-separated attributes: signature str, signature type (e.g., Android service name), and signature confidence (high or low).
In our detection, only apks matched high-confidence signatures were counted. 

**Proxy Programs**.
[final_proxy_apks.json](/datasets/final_proxy_apks.json) lists the detected apks along with its metadata. Below shows an example along with comments.
```bash
{
    // The date when this apk was captured
    "date": null,
    // SHA256 hash value for the apk payload
    "id": "3b2bab7ad955d2a71a774e3d269fe6e868dad01ddd8a4c1ec2d4f3e3791214ac",
    // You can ignore this field since it is the unique name we used to store the apk locally 
    "name": "com.wGSTRegistrationfree_7921336_1980-01-01_1214ac.apk",
    // The corresponding Android app id
    "pkg_id": "com.wGSTRegistrationfree_7921336",
    // Providers from which this apk has integrated the respective proxy SDKs
    // An apk can integrate multiple proxy SDKs from different proxy providers
    "proxy_providers": [
        "monkeysocks.net"
    ],
    // Where this apk was downloaded from
    "sources": [
        "androzoo"
    ]
}
```
## Source code
We are preparing the source code for release, and will update here once it is ready.

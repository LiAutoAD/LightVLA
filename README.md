# LightVLA: The Better You Learn, The Smarter You Prune

## 🚀 Towards Efficient Vision-language-action Models via Differentiable Token Pruning

[![License](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)

🌟 News
-----

- **[2026-01-31]** LightVLA has been accepted by **ICRA 2026**! 🎉


## 📝 Abstract

**LightVLA** is an innovative, simple yet effective differentiable token pruning framework designed for **Vision-Language-Action (VLA)** models. While VLA models have demonstrated impressive capabilities in executing real-world robotic tasks, their deployment on resource-constrained platforms is often bottlenecked by the heavy attention-based computation over large sets of visual tokens. LightVLA addresses this challenge through **adaptive, performance-driven visual token pruning**: it generates dynamic queries to evaluate the importance of visual tokens and employs Gumbel softmax for differentiable token selection. Through fine-tuning, LightVLA learns to retain the most informative visual tokens while pruning those that do not contribute to task execution, thereby **simultaneously improving efficiency and performance**. Notably, LightVLA requires no heuristic magic numbers and introduces no additional trainable parameters, making it compatible with modern inference frameworks. Experimental results show that LightVLA outperforms various VLA models and existing token pruning methods across diverse tasks on the LIBERO benchmark, achieving higher success rates with significantly reduced computational overhead. Specifically, LightVLA reduces FLOPs and latency by 59.1% and 38.2% respectively, with a 2.6% improvement in task success rate.

![framework_lightVLA.jpg](framework_lightVLA.jpg)

## 🔗 Project Links

*   **Project Website:** [https://liauto-research.github.io/LightVLA/](https://liauto-research.github.io/LightVLA/)
*   **Paper (arXiv):** [https://arxiv.org/abs/2509.12594](https://arxiv.org/abs/2509.12594)
*   **Example Video:** [https://cloud.tsinghua.edu.cn/f/1e3f4ab2bd7345768a6e/](https://cloud.tsinghua.edu.cn/f/1e3f4ab2bd7345768a6e/)
*   **Code (GitHub):** [https://github.com/LiAutoAD/LightVLA](https://github.com/LiAutoAD/LightVLA)
*   **Checkpoints (HuggingFace):** [https://huggingface.co/TTJiang/models?search=lightvla](https://huggingface.co/TTJiang/models?search=lightvla)

## TL;DR

The core implementation of LightVLA is [here](https://github.com/LiAutoAD/LightVLA/blob/main/prismatic/extern/hf/modeling_prismatic.py#L49).

## 💡 Key Features & Approach

LightVLA's core lies in its unique adaptive pruning mechanism, aimed at optimizing the efficiency and performance of VLA models:

*   **Adaptive, Performance-Driven Pruning:** LightVLA generates dynamic queries to assess the importance of visual tokens and utilizes Gumbel softmax for differentiable token selection. This approach enables the model to intelligently identify and retain crucial visual information for task execution while discarding redundant tokens.
*   **Dual Benefits of Efficiency and Performance:** By learning pruning strategies during fine-tuning, LightVLA not only significantly reduces computational overhead (FLOPs and latency) but also improves task success rates on the LIBERO benchmark, achieving a win-win in both efficiency and performance.
*   **No Additional Parameters:** A major advantage of LightVLA is its design, which does not rely on any heuristic magic numbers and introduces no additional trainable parameters. This makes it seamlessly integrable with existing modern inference frameworks, facilitating easy deployment and application.

## 📊 Experimental Results

LightVLA demonstrates exceptional performance improvements and efficiency optimizations on the LIBERO benchmark. Here's a comparison of key metrics:

| Metric                 | Improvement/Reduction |
| :--------------------- | :-------------------- |
| **FLOPs (Floating Point Operations)** | **↓ 59.1%**           |
| **Latency**            | **↓ 38.2%**           |
| **Task Success Rate**  | **↑ 2.6%**            |

These results highlight LightVLA's powerful ability to enhance the efficiency of VLA models while maintaining or even improving task execution performance.

## 🛠️ System Requirements

### Inference

*   1 GPU with ~16 GB VRAM for LIBERO sim benchmark tasks.

### Training

*   Between 1-8 GPUs with 27-80 GB, depending on the desired training setup (with default bfloat16 data type). See the [OpenVLA-OFT FAQ](https://openvla-oft.github.io/) for details.

## ⬇️ Installation

Please refer to the [SETUP.md](SETUP.md) file for detailed instructions on setting up the conda environment.

## 🚀 Training and Evaluation

Please refer to the [LIBERO.md](LIBERO.md) file for detailed instructions on fine-tuning/evaluating on LIBERO simulation benchmark task suites.

## 🤝 Support

If you encounter any issues, please feel free to open a new [GitHub Issue](https://github.com/LiAutoAD/LightVLA/issues).

## 📝 Citation

If you use our code or methods in your research or work, please cite our paper:

```bibtex
@misc{jiang2025betterlearnsmarterprune,
      title={The Better You Learn, The Smarter You Prune: Towards Efficient Vision-language-action Models via Differentiable Token Pruning}, 
      author={Titong Jiang and Xuefeng Jiang and Yuan Ma and Xin Wen and Bailin Li and Kun Zhan and Peng Jia and Yahui Liu and Sheng Sun and Xianpeng Lang},
      year={2025},
      eprint={2509.12594},
      archivePrefix={arXiv},
      primaryClass={cs.RO},
      url={https://arxiv.org/abs/2509.12594}, 
}
```

## 📜 License

This project is licensed under the [MIT License](LICENSE). Please see the `LICENSE` file in the project root for details.

## Acknowledgements

This work is built upon the wonderful [OpenVLA-OFT](https://openvla-oft.github.io/) project. Special thanks to Moo Jin Kim, Chelsea Finn, and Percy Liang for their contributions.

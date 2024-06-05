
<h2 align="center">
  <img src='./assets/bench2drive.jpg'>
</h2>

<h2 align="center">
  <a href="https://thinklab-sjtu.github.io/Bench2Drive/">Website</a> |
  <a href="https://huggingface.co/datasets/rethinlab/Bench2Drive">Huggingface</a> |
  <a href="https://github.com/Thinklab-SJTU/Bench2Drive">arXiv</a> |
  <a href="https://discord.gg/uZuU3JXVNV">Discord</a>
</h2>

![overview](./assets/overview.jpg)


<h2 align="center">
What can Bench2Drive provide ?
</h2>

[![Bench2Drive](https://i.ytimg.com/vi/-osdzJJs2g0/maxresdefault.jpg)](https://www.youtube.com/watch?v=-osdzJJs2g0 "Bench2Drive")

#####
## Table of Contents: <a name="high"></a>
1. [News](#News)
2. [Dataset](#Dataset)
3. [Benchmark](#Benchmark)
4. [License](#license)
5. [Citation](#citation)

## News <a name="news"></a>
  - [2024/06/05] Bench2Drive realases the Full (10000 clips), evaluation tools, baseline code and benchmark results.
  - [2024/04/27] Bench2Drive releases the Mini (10 clips) and Base (1000 clips) split of the official training data.

## Dataset <a name="dataset"></a>
  - The datasets has 3 subsets, namely Mini (10 clips), Base (1000 clips) and Full (10000 clips), to accommodate different levels of computational resource.
  - [Detailed explanation](docs/anno.md) of dataset structure, annotation information, and visualization of data.

| Subset  | Hugging Face<img src="./assets/hf-logo.png" alt="Hugging Face" width="18"/> | Baidu Cloud<img src="https://nd-static.bdstatic.com/m-static/v20-main/favicon-main.ico" alt="Baidu Yun" width="18"/> | Approx. Size |
| :---: |  :---: | :---: | :---: |
| Mini |   [Download script](https://github.com/Thinklab-SJTU/Bench2Drive/blob/main/tools/download_mini.sh) | [Download script](https://github.com/Thinklab-SJTU/Bench2Drive/blob/main/tools/download_mini.sh) |  4G |
| Base |  [Hugging Face Link](https://huggingface.co/datasets/rethinlab/Bench2Drive) |  [Baidu Cloud Link](https://pan.baidu.com/s/1ZIL-MPhLbgdBYmHkHncn8Q?pwd=1234) |  407G |
| Full |  [Hugging Face Link](https://huggingface.co/datasets/rethinlab/Bench2Drive-Full)   |  Uploading | 4T |

## Baseline Code
  - [Uniad/VAD in Bench2Drive]()
  - [TCP/ADMLP in Bench2Drive]()

## Eval Tools
  - Add your agent to leaderboard/team_code/your_agent.py
  - Debug Mode
    ```
    # Verify the correctness of the team agent， need to set GPU_RANK, TEAM_AGENT, TEAM_CONFIG
    bash /leaderboard/scripts/run_evaluation_debug.sh
    ```
  - Eval Mode
    ```
    # Please set TASK_NUM, GPU_RANK_LIST, TASK_LIST, TEAM_AGENT, TEAM_CONFIG, recommend GPU:Task(1:2).
    bash /leaderboard/scripts/run_evaluation_multi.sh 
    ```
  - Visualization 
    ```
    python tools/generate_video.py -f your_rgb_folder/
    ```
  - Metric
    ```
    # Merge eval json and get driving score and success rate
    python tools/merge_reoute_json.py -f your_json_folder/

    # Get multi-ability results
    python tools/ability_benchmark.py -r merge.json
    ```

## Benchmark <a name="benchmark"></a>

![benchmark](./assets/benchmark.jpg)

## License <a name="license"></a>

All assets and code are under the [Apache 2.0 license](./LICENSE) unless specified otherwise.

## Citation <a name="citation"></a>

Please consider citing our papers if the project helps your research with the following BibTex:

```bibtex
@article{jia2024bench,
  title={Bench2Drive: Towards Multi-Ability Benchmarking of Closed-Loop End-To-End Autonomous Driving},
  author={Xiaosong Jia and Zhenjie Yang and Qifeng Li and Zhiyuan Zhang and Junchi Yan},
  journal={\url{https://github.com/Thinklab-SJTU/Bench2Drive}},
  year={2024}
}

@article{li2024think,
  title={Think2Drive: Efficient Reinforcement Learning by Thinking in Latent World Model for Quasi-Realistic Autonomous Driving (in CARLA-v2)},
  author={Qifeng Li and Xiaosong Jia and Shaobo Wang and Junchi Yan},
  journal={arXiv preprint arXiv:2402.167200},
  year={2024}
}
```


# OpenLab Skill

[中文说明](README.zh-CN.md)

OpenLab Skill is an open agent skill for experiment and course-report writing, inspired by the practice of using an agent to deliver an entire experiment report end-to-end. Its goal is to raise efficiency and leave the truly important time to observing the experiment process and thinking about the results.

OpenLab Skill is a generic skill. It abstracts the base process of a typical experiment and can serve as a simple framework for extracting your own workflow skills later. Its principle is a single, self-contained four-stage main spine (Initialization → Clarify requirements → Processing → Completion). The main agent never assumes the user's intent: at each stage it waits for the user to choose Continue, Return, Other, or Stop. Any input other than those four explicit choices is treated as Other and routed to a free-input subagent capped at two rounds. Toolchain installation and unexpected situations during the experiment are wrapped as subagents that run until they succeed. Choosing Stop at any stage exits the skill. The diagram below illustrates this.

![principle](picture/principle.svg)








## Scope and Safety

> **Recommendation**: Before using this Skill, back up a copy of the experiment folder. Although the Skill limits how the experiment process can interfere with the original input data, for experiment safety it is still recommended to back up first, run the whole flow in the backup folder, and keep the original experiment folder untouched.

**Important**: It explicitly forbids fabricating measurements, screenshots, references, software output, or verification conclusions, and is not responsible for any results produced by the user.

This Skill assists with execution, evidence preservation, reproducibility, analysis, and documentation, but does not provide authoritative certification of scientific validity, does not replace qualified professional review, does not bypass software licensing, and cannot make work that was not actually performed compliant. The skill may use vision models (for example, to understand image input) and some automated operations (for example, Computer Use supported by Codex). Please confirm the security of the experiment environment to prevent privacy leakage.



## License

The project is released under the [MIT License](LICENSE). Third-party software, templates, datasets, and services retain their own licenses and are not bundled with this project by default.


Recent research in de novo antibody design has shifted away from improving the accuracy of individual models and toward optimizing the overall design pipeline. While generative models such as RFdiffusion have expanded the design space through epitope conditioning, many studies still rely on single-shot frameworks that fail to systematically incorporate design failures. This project aims to analyze why closed-loop optimization structures are increasingly adopted and to evaluate how failure-handling strategies affect the experimental feasibility of de novo antibody design.

To explore this question in practice, I selected six to eight representative studies on de novo antibody and protein design published between 2023 and 2025 and examined them using a unified analytical framework. The analysis focused on pipeline structure, failure-handling strategies, conditioning methods, and the presence of iterative refinement. To further clarify the differences between single-shot and closed-loop design approaches, I also implemented a simple toy simulation that visualizes how iterative feedback influences design efficiency.

The analysis indicates that the primary bottleneck in de novo design lies not in model prediction accuracy, but in pipeline architectures that fail to incorporate unsuccessful designs into subsequent iterations. In single-shot approaches, failed designs are discarded and provide no guidance for future attempts. In contrast, closed-loop frameworks transform failure into constraints or data, enabling iterative refinement and progressively improving design efficiency. These findings suggest that closed-loop optimization is not merely an optional performance enhancement, but a necessary structural condition for translating de novo antibody design into realistic experimental workflows. Overall, this project illustrates a broader shift in bioinformatics research from optimizing individual models to designing robust, system-level pipelines.


## Key Conclusions from the Annotated Paper Review  (Synthesis of 6–8 Studies)


1. Performance limitations in de novo design arise from pipeline structure, not model accuracy.

A comparative analysis of multiple de novo antibody and protein design studies showed that design failures were primarily driven not by insufficient predictive accuracy of individual models, but by pipeline architectures that failed to reflect unsuccessful outcomes in subsequent design cycles. In single-shot approaches, failed designs were filtered out during validation and did not accumulate as learning signals for future iterations.

Conclusion: The main bottleneck in de novo design is not model performance, but failure-handling strategy.



2. RFdiffusion expands design scope, but does not resolve failure accumulation.

RFdiffusion-based approaches significantly broaden the design space through epitope conditioning and CDR loop generation, enabling exploration beyond traditional library-based methods. However, when implemented within a single-shot architecture, failed designs are still discarded, preventing systematic improvement across iterations.

Conclusion: RFdiffusion increases design freedom but does not guarantee iterative optimization.



3. All studies that reuse failure as data adopt a closed-loop structure.

Among the analyzed papers, every study that explicitly reused failed designs as constraints or training signals for subsequent designs employed a closed-loop or lab-in-the-loop architecture. These studies consistently demonstrated gradual improvements in design success rates through iterative cycles of generation, prediction, experimental evaluation, and redesign.

Conclusion: Designs that meaningfully leverage failure inherently presuppose a closed-loop structure.



4. Closed-loop design is not a performance enhancement, but a mechanism for experimental realism.

Across the reviewed literature, the primary function of closed-loop architectures was not to produce optimal designs in a single attempt, but to reduce experimental costs and improve exploration efficiency in biological systems where failure is unavoidable. This reframes closed-loop optimization as a structural necessity rather than an optional refinement.

Conclusion: Closed-loop design is not a “nice-to-have,” but a prerequisite for experimental feasibility.



5. The research focus is shifting from better models to better-designed processes.

Taken together, the analyzed studies indicate a clear trend toward integrating design, validation, and redesign into unified, cyclical pipelines, rather than prioritizing isolated improvements in model accuracy. This reflects a broader transition in bioinformatics research from algorithm-centric development to system-level pipeline design.

Conclusion: The core of current de novo design research lies in pipeline architecture, not individual models.


## Pipeline Comparison
<img width="1760" height="1056" alt="closed-loop chart" src="https://github.com/user-attachments/assets/2a4b78bb-e901-40ff-a9ff-5d3306a4d778" />





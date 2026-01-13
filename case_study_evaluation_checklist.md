# Mini Case Study: Evaluation of an Agentic AI System for Predictive Maintenance in Manufacturing

This document demonstrates how to apply the three-dimensional taxonomy (Scope, Methodology, and Analysis) to evaluate an agentic AI system in manufacturing. We use an **imaginary use case** of a predictive maintenance agent for CNC machines.

---

## Use Case Description

**System**: Predictive Maintenance Agent for CNC Machine Monitoring  
**Purpose**: Monitors real-time sensor data, identifies anomalies, reasons about failures, and recommends maintenance actions using LLM-based reasoning.

**Key Capabilities**:
- Real-time sensor monitoring (temperature, vibration, power consumption)
- Anomaly detection and fault reasoning
- Natural language interaction with operators
- Integration with MES/ERP systems for maintenance scheduling
- Multi-step reasoning about failure modes and root causes

---

## Evaluation Checklist According to Proposed Taxonomy

### I. SCOPE — What is evaluated

#### ✅ 1. Output Quality
- [ ] **Fault detection accuracy**: Precision, recall, F1-score for actual faults vs. false alarms
- [ ] **Recommendation correctness**: Validation against expert maintenance protocols
- [ ] **Query response accuracy**: Accuracy of answers to operator questions about machine status
- [ ] **Task completion rate**: Percentage of maintenance queries successfully resolved
- [ ] **Baseline comparison**: Comparison against rule-based systems or traditional ML approaches

**Example Metrics**: 92% fault detection accuracy (vs. 85% baseline), 88% recommendation correctness, 90% query accuracy (LLM-as-judge + human validation)

---

#### ✅ 2. Cost
- [ ] **Latency**: Average response time for queries and recommendations
- [ ] **Token usage**: API calls and token consumption per interaction
- [ ] **Energy consumption**: Compute and inference energy costs
- [ ] **Operational costs**: API pricing, infrastructure, and maintenance overhead

**Example Metrics**: 1.2s average latency, ~2,500 tokens/interaction, 0.05 kWh per 100 queries, $0.15 per recommendation

---

#### ✅ 3. Agentic Capabilities
- [ ] **Planning/Reasoning**: Multi-step reasoning chains for fault diagnosis
- [ ] **Memory**: Retention of historical maintenance patterns and machine-specific context
- [ ] **Tool use**: Integration with sensor APIs, MES systems, documentation databases
- [ ] **Self-reflection**: Ability to revise recommendations based on feedback
- [ ] **Multi-agent coordination** (if applicable): Coordination with scheduling agents or other maintenance agents

**Example Metrics**: 4-6 step reasoning chains, 95% memory retention accuracy, 98% tool use success rate, 15% self-correction rate

---

#### ✅ 4. Reliability
- [ ] **Robustness to sensor noise**: Performance under varying data quality conditions
- [ ] **Error handling**: Graceful degradation when sensors fail or data is missing
- [ ] **Hallucination detection**: Rate of fabricated or incorrect information in responses
- [ ] **Stability**: Consistency of recommendations across similar scenarios
- [ ] **Recovery from failures**: Ability to resume operation after system errors

**Example Metrics**: 85% accuracy maintained with 20% sensor noise, <2% hallucination rate, 90% consistency across identical scenarios, <5s recovery time

---

#### ✅ 5. Safety and Ethics
- [ ] **Guarded tool use**: Critical actions (e.g., machine shutdown) require operator approval
- [ ] **Privacy compliance**: Data handling adheres to GDPR/industrial data protection standards
- [ ] **Fairness**: No bias in recommendations across different machine types or operators
- [ ] **Transparency**: Explainability of recommendations and decision rationale
- [ ] **Regulatory compliance**: Adherence to manufacturing safety standards

**Example Metrics**: 100% critical actions require operator confirmation, zero unauthorized data access incidents, no significant bias across machine types (p > 0.05), 95% explainability with reasoning chains

---

#### ✅ 6. User Experience
- [ ] **Usability**: Operator ease of use and learning curve
- [ ] **Trust**: Operator confidence in recommendations (survey-based)
- [ ] **Perceived helpfulness**: Subjective ratings of system utility
- [ ] **Expert validation**: Maintenance expert ratings of recommendation quality
- [ ] **Adoption rate**: Percentage of operators using the system regularly

**Example Metrics**: 82/100 SUS score, 4.2/5.0 trust rating (operator survey), 88% expert validation (rated "helpful" or "very helpful"), 75% weekly adoption rate

---

### II. METHODOLOGY OF EVALUATION

#### ✅ 7. Data and Benchmarks
- [ ] **Dataset type**: Synthetic, real-world, or hybrid
- [ ] **Data distribution**: Coverage of failure modes, machine types, and operational conditions
- [ ] **Benchmark design**: Standardized test suite with ground truth labels
- [ ] **Data split**: Train/validation/test splits and temporal considerations
- [ ] **Reproducibility**: Public availability or detailed documentation of datasets

**Example Approach**: Hybrid dataset (60% real sensor data, 40% synthetic failure scenarios), 5 machine types, 12 failure modes, 3 operational conditions, 500 test scenarios with expert-validated ground truth, temporal split (2023-2024 training, 2025 testing)

---

#### ✅ 8. Environment
- [ ] **Environment type**: Simulation, controlled lab, hybrid testbed, or industrial pilot
- [ ] **Realism**: Fidelity to actual manufacturing conditions
- [ ] **Controllability**: Ability to inject faults and test scenarios
- [ ] **Scalability**: Number of machines and concurrent interactions

**Example Approach**: Hybrid testbed (3 physical CNC machines + digital twin simulation), real sensor data with simulated fault injection, programmable fault scenarios (sensor failures, anomalies), tested with up to 10 concurrent machines

---

#### ✅ 9. Evaluator
- [ ] **Automated metrics**: Accuracy, precision, recall, latency, etc.
- [ ] **Human experts**: Maintenance engineers and operators
- [ ] **LLM-as-judge**: Calibrated LLM evaluation of response quality
- [ ] **Hybrid approach**: Combination of automated and human evaluation

**Example Approach**: Real-time metrics dashboard, 3 maintenance engineers evaluate 20% of recommendations, GPT-4 LLM-as-judge (calibrated against human ratings, r=0.85), automated metrics + monthly expert review

---

#### ✅ 10. Scale
- [ ] **Deployment scale**: Small/lab-scale, mid-scale hybrid, or pilot deployment
- [ ] **Longitudinal evaluation**: Performance over time (weeks/months)
- [ ] **Scalability testing**: Performance degradation with increased load
- [ ] **Industrial validation**: Real-world pilot with production machines

**Example Approach**: Mid-scale hybrid (3 physical + 7 simulated machines), 3-month longitudinal evaluation, tested up to 20 concurrent machines (simulated), 6-month industrial pilot at partner manufacturing facility

---

#### ✅ 11. Frameworks and Platforms
- [ ] **Evaluation framework**: Tools used (e.g., OpenAI Evals, LangGraph, custom)
- [ ] **Monitoring infrastructure**: Continuous evaluation and logging
- [ ] **Reproducibility tools**: Version control, experiment tracking
- [ ] **Integration**: Compatibility with existing MES/ERP systems

**Example Approach**: Custom evaluation framework with LangGraph for agent orchestration, real-time metrics dashboard, MLflow for experiment tracking, REST API integration with existing MES systems

---

### III. ANALYSIS OF EVALUATION

#### ✅ 12. Failure-Mode Analysis
- [ ] **Error categorization**: Classification of failure types (e.g., sensor errors, reasoning mistakes, tool failures)
- [ ] **Failure frequency**: Rate of different error types
- [ ] **Root cause analysis**: Understanding why failures occur
- [ ] **Failure scenarios**: Specific conditions that trigger failures
- [ ] **Mitigation strategies**: Proposed fixes for identified failure modes

**Example Analysis**: Error categories—sensor data misinterpretation (40%), reasoning chain errors (35%), tool API failures (15%), hallucinations (10%). Common failure scenario: High sensor noise + ambiguous symptoms → incorrect diagnosis. Mitigation: Enhanced noise filtering + multi-step verification

---

#### ✅ 13. Data Type Analysis
- [ ] **Data distribution**: Coverage across machine types, failure modes, operational conditions
- [ ] **Data quality**: Assessment of sensor data quality and completeness
- [ ] **Bias identification**: Potential biases in training/test data
- [ ] **Generalizability**: Performance across different data types and scenarios
- [ ] **Data limitations**: Gaps in coverage and their impact on evaluation

**Example Analysis**: Well-balanced distribution across 5 machine types; limited coverage of rare failure modes (<5% of data); 95% of sensor readings within expected ranges

---

#### ✅ 14. Impact Analysis
- [ ] **Production impact**: Effect on downtime, throughput, and production KPIs
- [ ] **Cost impact**: Reduction in maintenance costs, energy savings
- [ ] **Quality impact**: Improvement in product quality and defect rates
- [ ] **Safety impact**: Reduction in safety incidents and near-misses
- [ ] **Sustainability impact**: Energy efficiency and waste reduction
- [ ] **Business outcomes**: ROI, productivity gains, operator satisfaction

**Example Analysis**: 15% reduction in unplanned downtime, 8% increase in throughput, $50,000 annual savings in maintenance costs, 12% reduction in defect rates, zero safety incidents during pilot period, 5% reduction in energy consumption, 180% ROI over 12 months

---

## Recommendations for Future Evaluations

Based on this case study, key recommendations for evaluating agentic AI systems in manufacturing:

1. **Comprehensive Scope**: Evaluate beyond accuracy to include cost, capabilities, reliability, safety, and user experience
2. **Realistic Methodology**: Use hybrid testbeds that balance realism with controllability
3. **Thorough Analysis**: Conduct failure-mode, data-type, and impact analysis to understand limitations and value
4. **Standardized Reporting**: Use this checklist to ensure consistent and reproducible evaluations

---

## References

This case study is based on the taxonomy proposed in:
- Moradzadeh Farid, N., & Shafiee, S. (2026). "Evaluating Agentic AI Systems in Manufacturing: A Review of Taxonomy, Challenges and Future Directions." *2026 International Conference on Advances in Artificial Intelligence and Machine Learning (AAIML 2026)*, March 20-22, 2026, Tokyo, Japan. IEEE Conference Proceedings (to be published in IEEE Xplore).

For the full taxonomy and literature review, see the [main README](README.md).

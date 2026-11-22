# Generative AI (GA)

Source: https://info.standards.tech.gov.sg/control-catalog/gen-ai/ga/
Page last updated: 11 November 2026

Content © Government Technology Agency of Singapore, snapshotted from the public portal for grounding; canonical source is the live portal.

## GA-9 — External AI API services - Data classification

### Statement

If using external AI API services, apply the following requirements based on the security and sensitivity classification of the data being processed by the service.

CONFIDENTIAL data: Use only services served by models hosted in Singapore. Obtain a legally binding Zero Data Retention (ZDR) commitment from the API service provider(s). Access the service via environments authorized for CONFIDENTIAL data (e.g. GCC+).

CONFIDENTIAL (CLOUD-ELIGIBLE) or SENSITIVE-HIGH data: Use services served by models hosted in Singapore, or services whitelisted by GovTech. Obtain a legally binding Zero Data Retention (ZDR) commitment from the API service provider(s). Access the service via environments authorized for CONFIDENTIAL (CLOUD-ELIGIBLE) data (e.g. GCC).

RESTRICTED or SENSITIVE-NORMAL data: Obtain a legally binding Zero Data Retention (ZDR) commitment from the API service provider(s). Access the service via environments authorized for RESTRICTED data (e.g. GCC).

External AI API services refer to AI models and related services operated by third-party providers outside the Government, accessed via API as part of a generative AI workflow. These include generative AI models, as well as services that process data before, during or after model inference (e.g. embedding, reranking, web search, guardrail and post-processing services).

ZDR commitments by API service providers must be set out in the relevant agreement(s) governing the use of the service. The agreement(s) must require the provider not to log, store or retain input and output data for more than 24 hours for any purpose, or use such data for model training or improvement. ZDR commitments have already been obtained centrally for selected models and services available through GCC, GCC+, and PlatformAI. Product Teams using these services must only ensure that any configurations required for the ZDR terms to take effect are enabled.

### Recommendations

Use services served by models hosted in Singapore where possible.

Verify data security and sensitivity classification with data owner before using data with external AI API services.

Verify where models are hosted with AI API service providers before using their services.

Refer to the Annex below for further guidance on obtaining a legally binding ZDR commitment, configurations that may be required for ZDR terms to take effect, definitions, and exceptions.

### Risk statement

Government data processed by external AI API services may be exposed to unauthorised access, disclosure, misuse, or retention, particularly where the service is hosted overseas, or the provider is not legally bound to limit data retention and use.

## GA-10 — External AI SaaS - Data classification

### Statement

If using an external AI Software-as-a-Service (SaaS), apply the following requirements based on the security and sensitivity classification of the data being processed by the service.

CONFIDENTIAL (CLOUD-ELIGIBLE) or SENSITIVE-HIGH data: Use only services hosted in Singapore, or services whitelisted by GovTech. Obtain a legally binding Zero Data Retention (ZDR) commitment from the SaaS provider for data processed by AI models and related services before, during or after model inference (e.g. embedding, reranking, web search, guardrail and post-processing services).

RESTRICTED or SENSITIVE-NORMAL data: Obtain a legally binding ZDR commitment from the SaaS provider for data processed by AI models and related services before, during or after model inference (e.g. embedding, reranking, web search, guardrail and post-processing services).

ZDR commitments by SaaS providers must be set out in the relevant agreement(s) governing the use of the service. The agreement(s) must require that input and output data processed by the AI models and related services supporting the SaaS application’s generative AI functions are not logged, stored, or retained for more than 24 hours for any purpose, nor used for model training or improvement.

### Recommendations

Use services hosted in Singapore where possible.

Verify data security and sensitivity classification with data owner before using data with external SaaS.

Verify where AI models and related services are hosted with SaaS providers before using their services.

Refer to the Annex below for further guidance on obtaining a legally binding ZDR commitment, configurations that may be required for ZDR terms to take effect, definitions, and exceptions.

### Risk statement

Government data processed by external SaaS may be exposed to unauthorised access, disclosure, misuse, or retention, particularly where the service is hosted overseas, or the provider is not legally bound to limit data retention and use.

## GA-11 — Self-hosted generative AI models - Environments

### Statement

If self-hosting generative AI models in an environment you own or manage (e.g. GCC, GCC+, on-premise servers, local machines), use an environment permitted for the highest classification of data that will be processed by the model.

### Recommendations

Determine the highest classification of data that the model will process, and verify that the hosting environment is permitted to process and store data at that classification. Refer to applicable IM8 controls for the requirements that the hosting environment must meet for that data classification, including requirements relating to where the environment is hosted.

### Risk statement

Hosting a model in an environment that is not permitted for the classification of data it processes may expose classified data to unauthorised access or exfiltration.

## GA-12 — Self-hosted generative AI models - Model formats

### Statement

If self-hosting generative AI models in an environment you own or manage (e.g. GCC, GCC+, on-premise servers, local machines), use approved model formats [ insert: param, ga-12_prm_1 ].

### Recommendations

Any proposed deviations to L1 controls must be submitted to the AI Development Group (AIDG).

### Risk statement

Unsafe model formats may allow for arbitrary code execution and potential unauthorised access to the system. Approved model formats securely encode their models’ architecture and parameters.

### Parameters

| **ID** | **Type** | **Description** |
| --- | --- | --- |
| ga-12_prm_1 | Model formats (str) | Approved model formats for self-hosting |

## GA-13 — Self-hosted generative AI models - Model artefact scanning

### Statement

If self-hosting generative AI models in an environment you own or manage (e.g. GCC, GCC+, on-premise servers, local machines), scan model artefacts, including model files and loaders, for security vulnerabilities before use and at appropriate intervals throughout use. Remediate or mitigate vulnerabilities identified through the scans, and assess and accept any residual risks before use.

### Recommendations

Scan the model file for malicious code using model scanners updated with the latest signatures.

Update model loaders frequently to hinder attacks.

Before use, scan model loaders with Static Application Security Testing (SAST) tools to surface insecure coding patterns and known vulnerabilities.

During runtime, conduct further testing of model loaders with Dynamic Application Security Testing (DAST) tools to surface vulnerabilities that may only arise during execution.

Any proposed deviations to L1 controls must be submitted to the AI Development Group (AIDG).

### Risk statement

Open-weight or open-source models, and their associated artefacts (model files, model loaders), may contain security vulnerabilities, malicious modifications or backdoors that could enable arbitrary code execution, unauthorised access or other harmful behaviour. These risks remain even where models are hosted and managed by product teams in Government-controlled or isolated environments.

## GA-14 — Application safeguards - File uploads

### Statement

If file uploads are enabled, implement safeguards to prevent users from uploading files that, individually or collectively, exceed the data classification permitted for the generative AI application.

### Recommendations

Implement safeguards best suited to your use case, e.g.:

(1) Data Loss Protection (“DLP”) tools to monitor file uploads;

(2) Restricting bulk or batch file uploads, or requiring users to confirm the security and sensitivity classification of individual files before uploading them;

(3) Prompting users who upload large files to review their contents and the collective security and sensitivity classification.

Any proposed deviations to L1 controls must be submitted to the AI Development Group (AIDG).

### Risk statement

File uploads increase the risk of the generative AI application processing data above its permitted classification, for example where a higher-classified file is uploaded inadvertently, or multiple files are uploaded without considering their collective classification.

## GA-15 — Application safeguards - Consequential actions

### Statement

For generative AI applications capable of executing consequential actions, implement appropriate safeguards that prevent or limit the potential consequences of errors, and enable their timely detection and recovery.

An action is consequential where, if executed incorrectly, it could have wide-reaching effects, result in serious harm or adverse effects, or be difficult to reverse or recover from.

### Recommendations

Assess the reach, impact and reversibility of actions that the generative AI application can execute.

(1) Reach: the extent to which the effects of an action can extend beyond the immediate task or use

(2) Impact: the severity of harm or adverse effects that could result from incorrect execution

(3) Reversibility: the extent to which the effects of an action can be readily reversed or recovered from.

Implement appropriate safeguards based on the assessed risks. e.g.:

(1) Restricting the scope, permissions, frequency or scale of actions

(2) Providing action previews

(3) Maintaining appropriate logging and monitoring

(4) Implementing pause, rollback or other recovery mechanisms

(5) Requiring user confirmation or approval before execution where appropriate. Where this is not appropriate or feasible, implement other safeguards to restrict the scope and impact of the action and enable timely detection and recovery from errors.

Any proposed deviations to L1 controls must be submitted to the AI Development Group (AIDG).

### Risk statement

Without appropriate safeguards, erroneous or unintended AI actions may have wide-ranging or serious consequences, or result in effects that are difficult to reverse or recover from. This may cause operational, security, financial, legal, regulatory, service delivery or reputational harm.

## GA-16 — Application safeguards - Handling of web content

### Statement

Implement safeguards that ensure that any content retrieved from the live web is treated as untrusted reference data, cannot be interpreted or executed as instructions, and does not override or alter the generative AI application’s intended behaviour.

### Recommendations

Process externally retrieved content from the web through sanitisation, filtering, or guardrail checks before it is passed to the AI system. Remove or neutralise hidden prompts, prompt injections, embedded instructions, or other malicious content in retrieved data. Wrap retrieved content in explicit data boundaries and instruct the AI system to use it only as reference material.

Any proposed deviations to L1 controls must be submitted to the AI Development Group (AIDG).

### Risk statement

Content retrieved from the live web may contain malicious or hidden instructions, including indirect prompt injections. If interpreted as instructions by the generative AI application, such content may manipulate application behaviour, override intended instructions or safeguards, trigger unauthorised actions, or result in unsafe or unauthorised output.

## GA-17 — Application safeguards - Provenance of web content

### Statement

Record the provenance of any web content retrieved by the generative AI application, such that its sources and use can be traced and reconstructed for auditability, investigation, and accountability.

### Recommendations

Configure the application to capture structured event logs covering key user interactions, model or agent tool calls, classification of files uploaded, and all other actions relevant to the specific system or use case. Record web sources accessed by the AI system and sources shared with users. Ensure logs are tamper-resistant, access-controlled, retained according to organisational policy, and available for independent audit or incident investigation.

Any proposed deviations to L1 controls must be submitted to the AI Development Group (AIDG).

### Risk statement

Without provenance tracking, product teams may be unable to reconstruct AI system activity, verify the origin of outputs, investigate incidents, detect misuse, or demonstrate compliance with governance, security, and audit requirements.

## GA-18 — Application safeguards - Accuracy of output and actions

### Statement

Define appropriate accuracy targets for the application based on its specific use case and risks. Test the application’s output and actions against these standards. Implement measures or guardrails to ensure application meets these accuracy standards.

### Recommendations

Define what constitutes accurate performance for the use case.

Determine appropriate accuracy standards for generated output and (if applicable) actions taken.

Test and measure accuracy using clearly defined metrics, test scenarios, and acceptance criteria.

Implement measures or guardrails to reduce inaccuracy and/or the impact of inaccurate content.

Repeat testing and monitor accuracy following any updates to models, system prompts, connected tools, or other dependencies.

Refer to the Annex below for further guidance on accuracy testing methods and suitable measures.

Any proposed deviations to L1 controls must be submitted to the AI Development Group (AIDG).

### Risk statement

Generative AI models have the potential to ‘hallucinate’, i.e. present false, misleading, or out-of-date information as factually correct. This could cause misunderstandings, affect the delivery of Government policies, functions, or services, or have other negative implications where the information is relied on.

## GA-19 — Application safeguards - Safety of output and actions

### Statement

Identify safety risks relevant to the application based on its specific use case and risks. This may include malicious input that manipulate the application’s behaviour; harmful, toxic, discriminatory, illegal or otherwise inappropriate output; and unsafe or unauthorised actions. Define appropriate safety standards for the application based on the potential impact of these risks, test the application‘s output and actions against these standards, and implement measures or guardrails to meet them.

### Recommendations

Assess the nature and potential impact of each identified safety risk, including potential harm to persons, data, or systems.

Determine appropriate safety standards for generated output and (if applicable) actions taken.

Test and measure safety using clearly defined metrics, test scenarios or relevant adversarial or malicious input, and acceptance criteria.

Implement measures or guardrails to meet the defined safety standards, including to inspect and block prompt injections in user prompts and external content before use by the AI system. Use the AI system’s native prompt injection detection capabilities where available, such as Microsoft Defender Prompt Shield for Copilot. Where native capabilities are unavailable or insufficient, implement additional AI guardrail tools such as AWS Bedrock Guardrails, Azure Prompt Shield, or guardrails provided by GovTech.

Repeat testing and monitor safety following any updates to models, system prompts, connected tools, or other dependencies.

Refer to the Annex below for further guidance on safety testing methods and suitable measures.

Any proposed deviations to L1 controls must be submitted to the AI Development Group (AIDG).

### Risk statement

Generative AI applications may produce harmful, toxic, discriminatory, or otherwise inappropriate output, or execute unsafe or unauthorised actions. This may result from the behaviour of the underlying models or from malicious inputs, such as prompt injection, that manipulate the application into disregarding intended instructions or safeguards. This may cause harm to persons, result in unauthorised access to, disclosure, modification, or misuse of data, or adversely affect systems, services or operations.

## GA-20 — Application safeguards - Quality of output and actions

### Statement

Define what constitutes quality output for the generative AI application, such as relevance, coherence, clarity, appropriate tone and format, alignment with user intent, or successful completion of the intended task. Define appropriate output quality standards for the application based on the application’s use case, test the application‘s output and actions against these standards, and implement measures or guardrails to meet them.

### Recommendations

Identify the types of poor-quality performance that may arise based on the application’s core function and establish clear standards and acceptance criteria to ensure the application remains fit for purpose and users’ needs.

Test output and action quality using clearly defined metrics, test scenarios and acceptance criteria. The complexity and structure of testing should be tailored to the application’s risk profile.

Implement measures or guardrails to improve quality and reduce the impact of poor-quality outputs or actions.

Document the standards, testing approach, measures or guardrails implemented, and results. Measure and monitor quality and repeat testing after relevant model, prompt, tool, data source or other dependency updates.

Refer to the Annex below for further guidance on output quality testing methods and suitable measures.

Any proposed deviations to L1 controls must be submitted to the AI Development Group (AIDG).

### Risk statement

Generative AI models may produce poor quality output that is irrelevant, incoherent, unclear, or inappropriately presented, or execute actions that are misaligned with the user’s intent. This may reduce the usefulness and effectiveness of the application, and/or prevent it from performing its intended function.

## GA-21 — Deployment and use - Disclaimers on beta status

### Statement

When a generative AI application is made available to users for testing prior to deployment, inform users (1) of the experimental/beta status of the application, (2) that it is still undergoing testing and refinement, (3) and that it may have errors or vulnerabilities.

### Recommendations

Provide a clear disclaimer or label wherever users interact with the application, explaining that the application is still undergoing testing and refinement ahead of full deployment. Tailor the label to how users interact with the application, such as a banner for a web-based interface or a spoken disclaimer for a voice-based application.

### Risk statement

Users may over-rely on an application that is still undergoing testing if they are not informed that it may contain errors or vulnerabilities, increasing the risk of harm or reputational impact if the application does not perform as intended.

## GA-22 — Deployment and use - Disclaimers on risks and limitations

### Statement

When a generative AI application is made available to users, whether for testing or deployment, inform users of the risks and limitations of generative AI, including the possibility of inaccurate or fabricated output (hallucination).

### Recommendations

Provide users with a prominent disclaimer or label on the risk of inaccurate generative AI output. Present the disclaimer in a form appropriate to the application, such as a visual disclaimer for a web-based interface or a spoken disclaimer for a voice-based application.

Include clauses on the risk of inaccurate or fabricated output in the application’s Terms of Use.

Require users to explicitly acknowledge the risks of using generative AI before using the application, such as by selecting a checkbox or clicking an “I Agree” button.

Ensure that educational materials, such as documentation, guides, playbooks or workshops, highlight responsible use and best practices for users of the generative AI application.

Any proposed deviations to L1 controls must be submitted to the AI Development Group (AIDG).

### Risk statement

Users who are not informed of the risks and limitations of generative AI may over-rely on or trust inaccurate model-generated outputs.

## GA-23 — Deployment and use - Risk acceptance and approval

### Statement

Before progressing a generative AI application to closed beta or deployment, ensure that its risks are identified, assessed and addressed through the applicable IM8 controls, and that the following approval, declaration, and review requirements are met.

PUBLIC-FACING, AGENTIC, OR NATIONAL INTEREST/SII/CII USE CASES

(1) Closed beta: Obtain approval of the SSP from the Agency’s IDSC or IDSC-delegate. Declare the use case to the AI Development Group (AIDG).

(2) Deployment: Obtain and complete review by AIDG.

ALL OTHER USE CASES

(1) Closed beta: Obtain approval of the SSP from the Agency’s IDSC or IDSC-delegate.

(2) Deployment: Declare the use case to AIDG.

This control does not apply to use cases, agents or assistants built within the approved operating boundaries of a Qualifying Platform, which would be considered use of AI rather than development and deployment of AI.

### Recommendations

Agencies may refer to Section (E) of SNG (PMO) Circular No. 7/2026 for definitions of closed beta and deployment, and examples of the various use case categories.

### Risk statement

Without appropriate review, shortcomings in the safeguards implemented to address AI applications’ risks may not be identified. Applications may also not receive the level of scrutiny appropriate to their risk profile, particularly where their potential impact warrants additional oversight.

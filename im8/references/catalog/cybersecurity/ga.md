# Generative AI (GA)

Source: https://info.standards.tech.gov.sg/control-catalog/cybersecurity/ga/
Page last updated: 24 March 2026

Content © Government Technology Agency of Singapore, snapshotted from the public portal for grounding; canonical source is the live portal.

## GA-1 — Overseas-hosted GenAI API services

### Statement

Use only up to RESTRICTED and SENSITIVE NORMAL data with GenAI API services served by models hosted overseas.

### Recommendations

Verify data classification with data owner before using the data with overseas GenAI API services. Ensure that these API services are accessed only via environments authorised for up to RESTRICTED and SENSITIVE NORMAL data.

### Risk statement

Primary data is at greater legal, privacy, and exfiltration risk when in transit and processed by GenAI API services hosted in other countries.

## GA-2 — Singapore-hosted GenAI API services

### Statement

Use only up to CONFIDENTIAL and SENSITIVE HIGH data with GenAI API services served by models hosted in Singapore.

### Recommendations

Verify data classification with data owner before using the data with Singapore-hosted GenAI API services. Ensure that these API services are accessed only via environments authorised for up to CONFIDENTIAL and SENSITIVE HIGH data. Check documentation for whether cross-region inferencing or overseas processing occurs under certain conditions.

### Risk statement

Primary data carries legal, privacy, and exfiltration risk when in transit and processed by GenAI API services hosted in Singapore.

## GA-3 — Non-logging and non-training Agreement

### Statement

Obtain a legally-binding commitment from the GenAI API service provider that states that they do not log, store, nor retain input and output data, and that no input and output data are used for training GenAI models. Prompt caching (i.e. temporarily storing responses to frequently used prompts) is exempt from the above restriction on logging, storing, or retaining data, provided the cache time-to-live (TTL) is ≤ 24 hours.

### Recommendations

Ensure that the agreement covers all endpoints, parameters, outputs and models in use. Using GenAI API services provided by GCC 2.0 satisfies this control.

### Risk statement

Without a legally binding agreement, the GenAI service provider can access primary data or logs through automated or manual checks that can expose classified data, or they may use the data for further training of their GenAI models.

## GA-4 — Data classification for self-hosted GenAI models

### Statement

Ensure that GenAI models are hosted in an environment that can host the highest data classification of government data contained in the system that the model is deployed in.

### Recommendations

Refer to relevant IM8 SSPs for controls that need to be met before hosting government data of a given data classification in that environment (e.g. in a Singapore-hosted GCC environment.)

### Risk statement

Using GenAI models with data that is more classified than what its environment is permitted to hold may open up cybersecurity vulnerabilities for attackers to exfiltrate classified data.

## GA-5 — GenAI model formats and loaders

### Statement

Use approved formats (such as [ insert: param, ga-5_prm_1 ]) when using any open-weights GenAI models. Use approved loaders (such as [ insert: param, ga-5_prm_2 ]) to load open-weights GenAI models.

### Recommendations

Update GenAI model loaders frequently to hinder attacks.

### Risk statement

Insecure model formats or loaders have been shown to be potential threat vectors that may allow for arbitrary code execution. Failure to use more secure formats or loaders may result in potential unauthorised access to the system.

### Parameters

| **ID** | **Type** | **Description** |
| --- | --- | --- |
| ga-5_prm_1 | list of model formats (str) | An example list of approved model formats. |
| ga-5_prm_2 | list of model loaders (str) | An example list of approved model loaders. |

## GA-6 — File upload safeguards

### Statement

Implement file upload safeguards if file uploads are enabled in the system.

### Recommendations

Examples of safeguards include but are not limited to: (1) Implementing Data Loss Protection (“DLP”) tools to monitor document uploads, (2) Disabling bulk or batch file uploads, such as by preventing users from selecting multiple files with a single action, or by requiring users to confirm the data security/sensitivity classification of each file individually before uploading, (3) Prompting users who upload excessively large files to review file contents and their collective data security/sensitivity classification.

### Risk statement

Enabling file uploads in a generative AI application creates two key risks: (a) the possibility of sensitive data leaks if models are prompted to reveal information from uploaded files, and (b) the risk of exceeding permitted data classification levels — either by uploading multiple files without reassessing their collective classification, or by inadvertently uploading documents with a higher classification level due to human error.

## GA-7 — Evaluation of GenAI accuracy, safety, and output quality

### Statement

Test the accuracy, safety, and quality of the GenAI application's outputs, with clearly defined metrics, test scenarios, and criteria.

### Recommendations

Determine the adequate level of accuracy, safety, and output quality for your application. Develop tests to assess outputs on these dimensions. The complexity and structure of these tests should be tailored to the risk profile of your application. Document this approach and measure & monitor results after relevant model, prompt, and dependency updates.

### Risk statement

Failure to evaluate models, prompts, and their dependencies (such as tool integrations and retrieval-augmented generation (RAG) systems) can result in low-quality outputs after updates or configuration changes.

## GA-8 — Inform users about GenAI risks and limitations

### Statement

Require users to explicitly acknowledge the risk of inaccurate or fabricated outputs (hallucinations), such as selecting a checkbox or clicking on an 'I Agree' button before the application can be accessed.

### Recommendations

Include clauses about the risk of inaccurate / fabricated outputs in your Terms of Use. Indicate prominently in your application about the possibility of inaccurate or fabricated outputs. Ensure that educational materials, such as documentation, guides, playbooks, or workshops, highlight responsible use and best practices for users of the GenAI system.

### Risk statement

Uninformed users may trust inaccurate model-generated outputs.

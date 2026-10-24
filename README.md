# Assessment blueprint assembler

문항 품질·영역·난도·시간·중복 계열·정답 분포를 함께 만족하는 시험을 구성한다.

A focused executable resource for AI-assisted structured work. **Zero runtime dependencies, no API key, Node.js 22+.**

[Live workspace](https://proofnova.github.io/assessment-blueprint/) · [한국어 리소스 모음](https://proofnova.github.io/) · [Task contract](resource.json) · [Prior art](RESEARCH.md)

```sh
git clone https://github.com/proofnova/assessment-blueprint.git
cd assessment-blueprint
npm test
node cli.mjs example.json
```

## What it does

Reject invalid questions before bounded selection and answer-balance optimization.

A duplicated option or invalid answer index cannot enter a seemingly complete assessment.

## Connect a model

Import `execute` from `./run.mjs`. Expose this declared tool to your model, validate its tool name/input contract, execute it, and retain the returned JSON and input digest. Calculations and constraint checks are performed by the resource. No paid model or new agent framework is required.

[SKILL.md](SKILL.md) contains the workflow, interpretation and recovery procedure. [example.json](example.json) is a complete input; [cases.json](cases.json) contains worked and edge-case synthetic regression checks. The website executes the same code locally in a bounded Worker. It has no model or external data upload.

## Recovery and limits

Repair invalid items or supply missing blueprint cells; keep the selected item IDs for audit.

Underlying algorithms and task outcomes already exist in the alternatives. An existing tool configured for this exact task may remove the need for a separate project. Small synthetic tests cannot establish broad expertise or external demand. See [RESEARCH.md](RESEARCH.md). A plan/audit is not an external action or proof of actual user benefit.

## Contribute

Open an issue with a synthetic/redacted failing JSON input, expected result and Node version. Add a regression test and run `npm test`. Never include credentials or real private records in public examples.

MIT · Proofnova · 2026

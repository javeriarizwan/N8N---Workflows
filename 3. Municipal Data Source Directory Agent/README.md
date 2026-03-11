# AI-Powered Data Source Discovery Workflow

## Overview

This workflow is an AI-driven research and routing system built in n8n to identify the most relevant data source based on a user’s request.

It accepts a chat prompt, understands the intent, routes the request to the correct research agent, structures the result, stores it in Google Sheets, and exports the output as a CSV file.

The workflow is designed for situations where data may come from multiple source types and the system needs to intelligently choose the right path before saving results.

---

## What this workflow does

The workflow performs the following steps:

1. Receives a user request through chat
2. Detects the intent of the request
3. Extracts key location or search parameters
4. Routes the request to the correct specialized research agent
5. Collects the tool response
6. Normalizes the result into a structured format
7. Saves selected fields into Google Sheets
8. Converts the result into a downloadable CSV file

---

## Core workflow logic

### Chat trigger

The workflow starts when a user sends a message through the chat interface.

This serves as the main entry point for all incoming research requests.

### Intent detection agent

The central agent acts as an orchestrator.

Its job is to:

* understand what the user wants
* detect the correct request category
* extract important entities such as state or county
* call exactly one specialized tool
* return structured JSON output

It does not do the research itself. It only routes the task.

### Specialized research tools

The workflow includes multiple dedicated research agents, each focused on a different category of data discovery.

Examples of supported categories include:

* public records
* GIS / map-based data
* tax-related data
* code enforcement / service request data

Each tool is designed to search for the most automation-friendly source, such as:

* APIs
* structured downloads
* searchable public portals
* open data platforms

### Structured output parser

After a tool returns its result, the workflow normalizes the data into a consistent structure.

This ensures that outputs remain standardized even when the underlying sources vary.

### Google Sheets integration

The workflow appends important fields from the final output into a spreadsheet for tracking, logging, or downstream processing.

### File conversion

After storing the result, the workflow converts the output into CSV format for export or further automation.

---

## Key features

* AI-based intent detection
* Tool-based routing
* Structured output formatting
* Spreadsheet logging
* CSV export
* Modular research architecture
* Easy expansion for new data-source categories

---

## Example use cases

This workflow can be adapted for many research and automation tasks, including:

* discovering public datasets
* identifying official portals or APIs
* routing requests to the correct research module
* building internal data inventories
* preparing sources for later scraping or ingestion
* automating repetitive source discovery work

---

## Why this workflow is useful

Normally, discovering the right source is a manual process. Someone has to search, compare portals, inspect platforms, and decide which source is worth automating.

This workflow reduces that work by letting an AI agent:

* understand the request
* choose the right specialist path
* return a consistent result
* store the output automatically

It works well as a first-stage intelligence layer before full data extraction or scraping begins.

---

## Architecture summary

The workflow is built around five layers:

### 1. Input layer

Captures user requests via chat.

### 2. Orchestration layer

Uses an LLM-based agent to detect intent and choose the correct path.

### 3. Research layer

Uses specialized tools to find the most relevant data source.

### 4. Structuring layer

Normalizes the output into a fixed schema.

### 5. Delivery layer

Stores the result in Google Sheets and exports it as CSV.

---

## Tools used

* n8n
* OpenAI Chat Model
* Perplexity research tools
* Google Sheets
* CSV conversion node

---

## Business value

This workflow helps turn unstructured user requests into structured, actionable research output.

It is useful for teams that need:

* faster source discovery
* less manual research
* repeatable workflows
* cleaner data organization
* a scalable system for expanding into new source categories

---

## Future improvements

This workflow can be extended further by adding:

* duplicate checking before spreadsheet insert
* support for more data-source categories
* validation of returned endpoints
* confidence scoring
* retry/fallback routing
* automatic downstream ingestion workflows

---

## Summary

This is a modular AI workflow that combines chat input, intent detection, tool routing, structured output, spreadsheet storage, and file export into one automated pipeline.

In simple terms, it acts like a smart research assistant that can understand a request, find the right source path, and return the result in a usable format.

If you want, I can also turn this into a proper portfolio case study with sections like challenge, solution, workflow design, tools, and impact.

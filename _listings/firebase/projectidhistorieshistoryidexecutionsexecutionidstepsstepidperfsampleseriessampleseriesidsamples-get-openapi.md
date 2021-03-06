---
swagger: "2.0"
x-collection-name: Firebase
x-complete: 0
info:
  title: Firebase Get Sample Series
  description: |-
    Lists the Performance Samples of a given Sample Series - The list results are sorted by timestamps ascending - The default page size is 500 samples; and maximum size allowed 5000 - The response token indicates the last returned PerfSample timestamp - When the results size exceeds the page size, submit a subsequent request including the page token to return the rest of the samples up to the page limit

    May return any of the following canonical error codes: - OUT_OF_RANGE - The specified request page_token is out of valid range - NOT_FOUND - The containing PerfSampleSeries does not exist
  version: 1.0.0
host: '{project_id].firebaseio.co}'
basePath: /
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /{projectId}/histories/{historyId}/executions/{executionId}/steps/{stepId}/perfSampleSeries:
    get:
      summary: Get Sample Series
      description: |-
        Lists PerfSampleSeries for a given Step.

        The request provides an optional filter which specifies one or more PerfMetricsType to include in the result; if none returns all. The resulting PerfSampleSeries are sorted by ids.

        May return any of the following canonical error codes: - NOT_FOUND - The containing Step does not exist
      operationId: toolresults.projects.histories.executions.steps.perfSampleSeries.list
      x-api-path-slug: projectidhistorieshistoryidexecutionsexecutionidstepsstepidperfsampleseries-get
      parameters:
      - in: path
        name: executionId
        description: A tool results execution ID
      - in: query
        name: filter
        description: Specify one or more PerfMetricType values such as CPU to filter
          the result
      - in: path
        name: historyId
        description: A tool results history ID
      - in: path
        name: projectId
        description: The cloud project
      - in: path
        name: stepId
        description: A tool results step ID
      responses:
        200:
          description: OK
      tags:
      - Sample Series
    post:
      summary: Create Sample Series
      description: |-
        Creates a PerfSampleSeries.

        May return any of the following error code(s): - ALREADY_EXISTS - PerfMetricSummary already exists for the given Step - NOT_FOUND - The containing Step does not exist
      operationId: toolresults.projects.histories.executions.steps.perfSampleSeries.create
      x-api-path-slug: projectidhistorieshistoryidexecutionsexecutionidstepsstepidperfsampleseries-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: executionId
        description: A tool results execution ID
      - in: path
        name: historyId
        description: A tool results history ID
      - in: path
        name: projectId
        description: The cloud project
      - in: path
        name: stepId
        description: A tool results step ID
      responses:
        200:
          description: OK
      tags:
      - Sample Series
  /{projectId}/histories/{historyId}/executions/{executionId}/steps/{stepId}/perfSampleSeries/{sampleSeriesId}:
    get:
      summary: Get Sample Series
      description: |-
        Gets a PerfSampleSeries.

        May return any of the following error code(s): - NOT_FOUND - The specified PerfSampleSeries does not exist
      operationId: toolresults.projects.histories.executions.steps.perfSampleSeries.get
      x-api-path-slug: projectidhistorieshistoryidexecutionsexecutionidstepsstepidperfsampleseriessampleseriesid-get
      parameters:
      - in: path
        name: executionId
        description: A tool results execution ID
      - in: path
        name: historyId
        description: A tool results history ID
      - in: path
        name: projectId
        description: The cloud project
      - in: path
        name: sampleSeriesId
        description: A sample series id
      - in: path
        name: stepId
        description: A tool results step ID
      responses:
        200:
          description: OK
      tags:
      - Sample Series
  /{projectId}/histories/{historyId}/executions/{executionId}/steps/{stepId}/perfSampleSeries/{sampleSeriesId}/samples:
    get:
      summary: Get Sample Series
      description: |-
        Lists the Performance Samples of a given Sample Series - The list results are sorted by timestamps ascending - The default page size is 500 samples; and maximum size allowed 5000 - The response token indicates the last returned PerfSample timestamp - When the results size exceeds the page size, submit a subsequent request including the page token to return the rest of the samples up to the page limit

        May return any of the following canonical error codes: - OUT_OF_RANGE - The specified request page_token is out of valid range - NOT_FOUND - The containing PerfSampleSeries does not exist
      operationId: toolresults.projects.histories.executions.steps.perfSampleSeries.samples.list
      x-api-path-slug: projectidhistorieshistoryidexecutionsexecutionidstepsstepidperfsampleseriessampleseriesidsamples-get
      parameters:
      - in: path
        name: executionId
        description: A tool results execution ID
      - in: path
        name: historyId
        description: A tool results history ID
      - in: query
        name: pageSize
        description: The default page size is 500 samples, and the maximum size is
          5000
      - in: query
        name: pageToken
        description: Optional, the next_page_token returned in the previous response
      - in: path
        name: projectId
        description: The cloud project
      - in: path
        name: sampleSeriesId
        description: A sample series id
      - in: path
        name: stepId
        description: A tool results step ID
      responses:
        200:
          description: OK
      tags:
      - Sample Series
x-streamrank:
  polling_total_time_average: 0
  polling_size_download_average: 0
  streaming_total_time_average: 0
  streaming_size_download_average: 0
  change_yes: 0
  change_no: 0
  time_percentage: 0
  size_percentage: 0
  change_percentage: 0
  last_run: ""
  days_run: 0
  minute_run: 0
---
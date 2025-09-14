# LLM Experiment Environment Specification

## 1. FUNCTIONAL REQUIREMENTS

### 1.1 Core System Overview
**Deliverable**: Single HTML file with embedded CSS/JS for testing 4 prompting frameworks against LLM tool-calling scenarios.

**Primary Objectives**:
- Compare effectiveness of 4 distinct prompting frameworks
- Evaluate LLM performance across 3 difficulty tiers
- Provide quantitative metrics for framework comparison
- Enable reproducible experimentation without external dependencies

### 1.2 System Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                    HTML Container                           │
├─────────────────────────────────────────────────────────────┤
│  ┌─────────────────┐  ┌─────────────────┐  ┌─────────────┐ │
│  │   UI Controller │  │ Simulation      │  │ Evaluation  │ │
│  │   - Framework   │  │ Engine          │  │ Metrics     │ │
│  │     Selection   │  │ - Mock LLM API  │  │ - Precision │ │
│  │   - Status Log  │  │ - Response Gen  │  │ - F1 Score  │ │
│  │   - Results     │  │ - Tool Calling  │  │ - Hit Rate  │ │
│  └─────────────────┘  └─────────────────┘  └─────────────┘ │
│                                                             │
│  ┌─────────────────────────────────────────────────────────┐ │
│  │              Test Battery Manager                       │ │
│  │  - Easy Tier (Basic tool calls)                        │ │
│  │  - Medium Tier (Multi-step scenarios)                  │ │
│  │  - Hard Tier (Complex reasoning + tools)               │ │
│  └─────────────────────────────────────────────────────────┘ │
└─────────────────────────────────────────────────────────────┘
```

### 1.3 Detailed Functional Requirements

#### 1.3.1 Framework Management
- **FR-001**: System SHALL support exactly 4 prompting frameworks
- **FR-002**: Each framework SHALL have distinct prompt templates
- **FR-003**: Framework selection SHALL be mutually exclusive per test run
- **FR-004**: System SHALL maintain framework-specific configuration

#### 1.3.2 Test Battery Execution
- **FR-005**: System SHALL execute tests across 3 difficulty tiers sequentially
- **FR-006**: Each tier SHALL contain 5-10 representative scenarios
- **FR-007**: Test execution SHALL be deterministic and repeatable
- **FR-008**: System SHALL support partial test runs (single tier)

#### 1.3.3 Simulation Engine
- **FR-009**: Mock LLM API SHALL generate realistic responses based on framework effectiveness
- **FR-010**: Response generation SHALL consider framework strengths/weaknesses
- **FR-011**: Tool calling simulation SHALL validate argument structure and types
- **FR-012**: System SHALL maintain response consistency for identical inputs

#### 1.3.4 Evaluation and Metrics
- **FR-013**: System SHALL calculate Tool Call Precision (correct tools/total attempts)
- **FR-014**: System SHALL calculate Argument F1 Score (precision + recall of arguments)
- **FR-015**: System SHALL calculate Ambiguity Hit Rate (successful ambiguous scenario handling)
- **FR-016**: Results SHALL be aggregated by framework and difficulty tier

#### 1.3.5 User Interface
- **FR-017**: UI SHALL provide framework selection interface
- **FR-018**: System SHALL display real-time test execution status
- **FR-019**: Results SHALL be presented in tabular format with sorting
- **FR-020**: Interface SHALL be responsive across desktop/tablet/mobile

## 2. PROMPTING FRAMEWORKS SPECIFICATION

### 2.1 Designer's Paradigm
**Philosophy**: Visual-spatial reasoning with structured decomposition
**Template Structure**:
```
DESIGN BRIEF: {scenario_description}
CONSTRAINTS: {technical_limitations}
COMPONENTS AVAILABLE: {tool_inventory}
DESIGN PROCESS:
1. Analyze requirements
2. Identify component relationships  
3. Select optimal tools
4. Validate design coherence
OUTPUT: {structured_tool_calls}
```
**Strengths**: Complex multi-tool scenarios, spatial reasoning
**Weaknesses**: Simple single-tool tasks, time-sensitive operations

### 2.2 Linguistic Imperative
**Philosophy**: Natural language flow with contextual reasoning
**Template Structure**:
```
Given the situation: {scenario_description}
I need to understand what actions are required.
Let me think through this step by step:
- What is the core objective?
- What tools can help achieve this?
- How do these tools work together?
Based on this analysis: {tool_calls}
```
**Strengths**: Ambiguous scenarios, contextual understanding
**Weaknesses**: Precise technical specifications, structured data

### 2.3 Managerial Directive
**Philosophy**: Goal-oriented execution with clear hierarchies
**Template Structure**:
```
OBJECTIVE: {scenario_description}
SUCCESS CRITERIA: {measurable_outcomes}
EXECUTION PLAN:
Phase 1: {primary_tools}
Phase 2: {secondary_tools}  
Phase 3: {validation_tools}
EXECUTE: {ordered_tool_calls}
```
**Strengths**: Multi-step workflows, clear objectives
**Weaknesses**: Creative problem-solving, flexible adaptation

### 2.4 Hip-Hop G-Funk Protocol
**Philosophy**: Rhythmic pattern recognition with creative synthesis
**Template Structure**:
```
Yo, check the scenario: {scenario_description}
Break it down to the beat:
🎵 What's the vibe? (analyze)
🎵 What tools we got? (inventory)
🎵 How we flow? (sequence)
🎵 Make it smooth: {tool_calls}
Keep it funky, keep it real! 🎵
```
**Strengths**: Pattern recognition, creative combinations
**Weaknesses**: Formal documentation, precise specifications

## 3. TEST BATTERY STRUCTURE

### 3.1 Easy Tier (Difficulty Level 1)
**Characteristics**: Single tool calls, clear objectives, minimal ambiguity

**Test Scenarios**:
1. **File Operations**: "Create a new file called 'report.txt'"
   - Expected Tool: `create_file`
   - Arguments: `{filename: "report.txt", content: ""}`

2. **Data Retrieval**: "Get the current weather for New York"
   - Expected Tool: `get_weather`
   - Arguments: `{location: "New York", units: "metric"}`

3. **Simple Calculation**: "Calculate 15% tip on $45.67"
   - Expected Tool: `calculate`
   - Arguments: `{operation: "multiply", values: [45.67, 0.15]}`

4. **Text Processing**: "Convert 'Hello World' to uppercase"
   - Expected Tool: `text_transform`
   - Arguments: `{text: "Hello World", operation: "uppercase"}`

5. **Basic Search**: "Find documents containing 'quarterly report'"
   - Expected Tool: `search_documents`
   - Arguments: `{query: "quarterly report", scope: "all"}`

### 3.2 Medium Tier (Difficulty Level 2)
**Characteristics**: Multi-step workflows, moderate ambiguity, tool chaining

**Test Scenarios**:
1. **Data Analysis Pipeline**: "Analyze sales data and create a summary report"
   - Expected Tools: `load_data` → `analyze_data` → `generate_report`
   - Requires proper sequencing and data passing

2. **Content Management**: "Find all images larger than 5MB and compress them"
   - Expected Tools: `search_files` → `filter_by_size` → `compress_images`
   - Requires conditional logic and batch processing

3. **Communication Workflow**: "Send meeting notes to team members who attended yesterday's standup"
   - Expected Tools: `get_meeting_attendees` → `retrieve_notes` → `send_email`
   - Requires data correlation and filtering

4. **System Maintenance**: "Check disk space and clean up old log files if needed"
   - Expected Tools: `check_disk_space` → `find_old_files` → `delete_files`
   - Requires conditional execution

5. **Research Task**: "Find recent articles about AI and summarize key findings"
   - Expected Tools: `search_articles` → `filter_by_date` → `extract_content` → `summarize`
   - Requires multi-step information processing

### 3.3 Hard Tier (Difficulty Level 3)
**Characteristics**: Complex reasoning, high ambiguity, adaptive tool selection

**Test Scenarios**:
1. **Adaptive Problem Solving**: "The system is running slowly - diagnose and fix the issue"
   - Multiple possible tool paths depending on diagnosis
   - Requires iterative investigation and adaptive responses

2. **Creative Content Generation**: "Create a marketing campaign for a new eco-friendly product"
   - Expected Tools: Variable based on creative approach
   - Requires synthesis of multiple information sources

3. **Complex Data Integration**: "Merge customer data from three different sources and identify duplicates"
   - Expected Tools: `load_multiple_sources` → `normalize_data` → `detect_duplicates` → `merge_records`
   - Requires sophisticated data handling logic

4. **Ambiguous Request**: "Make the website better"
   - Multiple valid interpretations and tool combinations
   - Tests framework's ability to handle vague requirements

5. **Emergency Response**: "Production server is down - restore service immediately"
   - Time-critical scenario with multiple possible approaches
   - Tests prioritization and rapid decision-making

## 4. EVALUATION METRICS

### 4.1 Tool Call Precision
**Definition**: Percentage of correct tool selections out of total tool calls
**Formula**: `Precision = (Correct Tools Called / Total Tools Called) × 100`
**Scoring**:
- Exact tool match: 1.0 point
- Functionally equivalent tool: 0.8 points
- Wrong tool: 0.0 points

### 4.2 Argument F1 Score
**Definition**: Harmonic mean of argument precision and recall
**Components**:
- **Precision**: `(Correct Arguments / Total Arguments Provided)`
- **Recall**: `(Correct Arguments / Total Required Arguments)`
- **F1**: `2 × (Precision × Recall) / (Precision + Recall)`

**Argument Scoring**:
- Exact match: 1.0 point
- Type correct, value close: 0.7 points
- Type correct, value wrong: 0.3 points
- Type wrong: 0.0 points

### 4.3 Ambiguity Hit Rate
**Definition**: Success rate in handling ambiguous or underspecified scenarios
**Calculation**: `Hit Rate = (Successful Ambiguous Scenarios / Total Ambiguous Scenarios) × 100`
**Success Criteria**:
- Appropriate clarification requests: Full credit
- Reasonable assumption with explanation: 0.8 credit
- Valid solution without clarification: 0.6 credit
- Invalid or no response: 0.0 credit

### 4.4 Composite Scoring
**Overall Framework Score**: Weighted average across all metrics
- Tool Call Precision: 40% weight
- Argument F1 Score: 35% weight  
- Ambiguity Hit Rate: 25% weight

## 5. UI/UX SPECIFICATIONS

### 5.1 Layout Structure
```
┌─────────────────────────────────────────────────────────────┐
│                    Header Bar                               │
│  LLM Experiment Environment    [Framework: ▼] [Run Tests]  │
├─────────────────────────────────────────────────────────────┤
│ ┌─────────────────┐ ┌─────────────────────────────────────┐ │
│ │   Test Status   │ │           Results Panel             │ │
│ │                 │ │                                     │ │
│ │ ● Easy Tier     │ │  Framework | Precision | F1 | Hit  │ │
│ │ ○ Medium Tier   │ │  ---------|----------|----|----- │ │
│ │ ○ Hard Tier     │ │  Designer |   85.2%  |0.78| 72% │ │
│ │                 │ │  Linguistic|  79.1%  |0.82| 89% │ │
│ │ Progress: 23%   │ │  Manager  |   91.3%  |0.71| 65% │ │
│ │ [████░░░░░░]    │ │  Hip-Hop  |   76.8%  |0.85| 94% │ │
│ └─────────────────┘ └─────────────────────────────────────┘ │
├─────────────────────────────────────────────────────────────┤
│                    Execution Log                            │
│ [12:34:56] Starting Easy Tier tests...                     │
│ [12:34:57] Designer's Paradigm: Test 1/5 - PASS           │
│ [12:34:58] Designer's Paradigm: Test 2/5 - FAIL           │
│ [12:34:59] Tool call precision: Expected create_file,      │
│            got search_documents                             │
└─────────────────────────────────────────────────────────────┘
```

### 5.2 Interactive Elements
- **Framework Selector**: Dropdown with 4 options + "All Frameworks"
- **Run Tests Button**: Triggers test execution, disabled during runs
- **Progress Indicators**: Real-time progress bars and status icons
- **Results Table**: Sortable columns, expandable rows for details
- **Log Panel**: Auto-scrolling, filterable by log level

### 5.3 Responsive Design
- **Desktop (>1024px)**: Full layout as shown above
- **Tablet (768-1024px)**: Stacked panels, condensed results table
- **Mobile (<768px)**: Single column, collapsible sections

## 6. SIMULATION ENGINE ARCHITECTURE

### 6.1 Mock LLM API Structure
```javascript
class MockLLMAPI {
  constructor() {
    this.frameworkEffectiveness = {
      'designers-paradigm': {
        easy: 0.85, medium: 0.78, hard: 0.72
      },
      'linguistic-imperative': {
        easy: 0.79, medium: 0.82, hard: 0.89
      },
      'managerial-directive': {
        easy: 0.91, medium: 0.71, hard: 0.65
      },
      'hip-hop-g-funk': {
        easy: 0.77, medium: 0.85, hard: 0.94
      }
    };
  }
}
```

### 6.2 Response Generation Logic
1. **Input Processing**: Parse scenario + framework combination
2. **Effectiveness Lookup**: Get framework effectiveness for difficulty tier
3. **Response Simulation**: Generate tool calls based on effectiveness probability
4. **Error Injection**: Introduce realistic errors based on framework weaknesses
5. **Consistency Maintenance**: Cache responses for identical inputs

### 6.3 Tool Call Validation
- **Schema Validation**: Check argument types and required fields
- **Semantic Validation**: Verify logical consistency of tool combinations
- **Context Validation**: Ensure tools are appropriate for scenario context

## 7. EDGE CASES AND CONSTRAINTS

### 7.1 Technical Constraints
- **File Size Limit**: Single HTML file must be < 2MB total
- **Module Size Limit**: Each logical module < 500 lines
- **Browser Compatibility**: Support Chrome 90+, Firefox 88+, Safari 14+
- **No External Dependencies**: All code embedded in single file
- **No Network Requests**: Fully self-contained simulation

### 7.2 Edge Cases
1. **Rapid Successive Runs**: Handle multiple test executions without conflicts
2. **Browser Tab Switching**: Maintain state during background execution
3. **Incomplete Test Runs**: Handle user interruption gracefully
4. **Invalid Framework Selection**: Validate input and provide fallbacks
5. **Memory Constraints**: Manage large result datasets efficiently
6. **Concurrent Execution**: Prevent multiple simultaneous test runs

### 7.3 Error Handling
- **Graceful Degradation**: Continue testing even if individual tests fail
- **User Feedback**: Clear error messages with actionable guidance
- **State Recovery**: Ability to resume from interruption points
- **Data Validation**: Comprehensive input validation with user-friendly errors

### 7.4 Performance Constraints
- **Test Execution Time**: Complete all tests within 30 seconds
- **UI Responsiveness**: Maintain <100ms response time for interactions
- **Memory Usage**: Stay under 50MB total memory consumption
- **CPU Usage**: Avoid blocking main thread for >16ms

## 8. MODULAR PSEUDOCODE WITH TDD ANCHORS

### 8.1 Core System Modules

#### 8.1.1 Framework Manager Module
```pseudocode
MODULE FrameworkManager {
  INTERFACE IFramework {
    name: String
    generatePrompt(scenario: Scenario): String
    parseResponse(response: String): ToolCall[]
    getEffectiveness(difficulty: DifficultyTier): Float
  }
  
  CLASS FrameworkRegistry {
    frameworks: Map<String, IFramework>
    
    FUNCTION registerFramework(framework: IFramework): Void
    FUNCTION getFramework(name: String): IFramework
    FUNCTION getAllFrameworks(): IFramework[]
  }
  
  // TDD Anchor: Test framework registration and retrieval
  TEST_SUITE FrameworkManagerTests {
    TEST "should register framework successfully"
    TEST "should retrieve registered framework"
    TEST "should throw error for unknown framework"
    TEST "should return all registered frameworks"
  }
}
```

#### 8.1.2 Test Battery Module
```pseudocode
MODULE TestBattery {
  ENUM DifficultyTier { EASY, MEDIUM, HARD }
  
  CLASS TestScenario {
    id: String
    description: String
    difficulty: DifficultyTier
    expectedTools: ToolCall[]
    ambiguityLevel: Float
    
    FUNCTION execute(framework: IFramework): TestResult
    FUNCTION validate(actualTools: ToolCall[]): ValidationResult
  }
  
  CLASS TestSuite {
    scenarios: TestScenario[]
    
    FUNCTION addScenario(scenario: TestScenario): Void
    FUNCTION getScenariosByDifficulty(tier: DifficultyTier): TestScenario[]
    FUNCTION executeAll(framework: IFramework): TestResult[]
  }
  
  // TDD Anchor: Test scenario execution and validation
  TEST_SUITE TestBatteryTests {
    TEST "should execute scenario with framework"
    TEST "should validate tool calls correctly"
    TEST "should filter scenarios by difficulty"
    TEST "should handle execution errors gracefully"
  }
}
```

#### 8.1.3 Simulation Engine Module
```pseudocode
MODULE SimulationEngine {
  CLASS MockLLMAPI {
    effectivenessMatrix: Map<String, Map<DifficultyTier, Float>>
    responseCache: Map<String, String>
    
    FUNCTION generateResponse(prompt: String, framework: String, difficulty: DifficultyTier): String
    FUNCTION simulateToolCalls(scenario: TestScenario, effectiveness: Float): ToolCall[]
    FUNCTION injectRealisticErrors(toolCalls: ToolCall[], errorRate: Float): ToolCall[]
  }
  
  CLASS ResponseGenerator {
    FUNCTION generateCorrectResponse(scenario: TestScenario): ToolCall[]
    FUNCTION applyFrameworkBias(toolCalls: ToolCall[], framework: IFramework): ToolCall[]
    FUNCTION addNoise(toolCalls: ToolCall[], noiseLevel: Float): ToolCall[]
  }
  
  // TDD Anchor: Test response generation and error injection
  TEST_SUITE SimulationEngineTests {
    TEST "should generate responses based on effectiveness"
    TEST "should inject errors at specified rate"
    TEST "should cache identical requests"
    TEST "should apply framework-specific biases"
  }
}
```

#### 8.1.4 Evaluation Metrics Module
```pseudocode
MODULE EvaluationMetrics {
  CLASS MetricsCalculator {
    FUNCTION calculateToolCallPrecision(expected: ToolCall[], actual: ToolCall[]): Float
    FUNCTION calculateArgumentF1Score(expected: ToolCall[], actual: ToolCall[]): Float
    FUNCTION calculateAmbiguityHitRate(scenarios: TestScenario[], results: TestResult[]): Float
    FUNCTION calculateCompositeScore(precision: Float, f1: Float, hitRate: Float): Float
  }
  
  CLASS ResultAggregator {
    FUNCTION aggregateByFramework(results: TestResult[]): Map<String, AggregatedResult>
    FUNCTION aggregateByDifficulty(results: TestResult[]): Map<DifficultyTier, AggregatedResult>
    FUNCTION generateSummaryReport(results: TestResult[]): SummaryReport
  }
  
  // TDD Anchor: Test metrics calculation accuracy
  TEST_SUITE EvaluationMetricsTests {
    TEST "should calculate precision correctly for perfect match"
    TEST "should calculate precision correctly for partial match"
    TEST "should calculate F1 score with proper precision/recall"
    TEST "should handle edge cases (empty results, no expected tools)"
  }
}
```

#### 8.1.5 UI Controller Module
```pseudocode
MODULE UIController {
  CLASS ExperimentController {
    frameworkManager: FrameworkManager
    testBattery: TestBattery
    simulationEngine: SimulationEngine
    metricsCalculator: MetricsCalculator
    
    FUNCTION initializeUI(): Void
    FUNCTION handleFrameworkSelection(frameworkName: String): Void
    FUNCTION startTestExecution(): Promise<TestResult[]>
    FUNCTION updateProgress(current: Integer, total: Integer): Void
    FUNCTION displayResults(results: TestResult[]): Void
  }
  
  CLASS StatusLogger {
    logContainer: HTMLElement
    
    FUNCTION logInfo(message: String): Void
    FUNCTION logError(message: String): Void
    FUNCTION logProgress(message: String): Void
    FUNCTION clearLog(): Void
  }
  
  // TDD Anchor: Test UI interactions and state management
  TEST_SUITE UIControllerTests {
    TEST "should initialize UI components correctly"
    TEST "should handle framework selection events"
    TEST "should update progress indicators"
    TEST "should display results in table format"
  }
}
```

### 8.2 Integration and System Tests

```pseudocode
TEST_SUITE SystemIntegrationTests {
  TEST "should execute complete test run for single framework" {
    // Arrange
    framework = new DesignersParadigm()
    testSuite = createEasyTierTests()
    
    // Act
    results = executeTestSuite(framework, testSuite)
    
    // Assert
    ASSERT results.length == testSuite.scenarios.length
    ASSERT all results have valid metrics
    ASSERT execution time < 10 seconds
  }
  
  TEST "should handle all frameworks across all difficulty tiers" {
    // Arrange
    frameworks = getAllFrameworks()
    allTests = getAllTestScenarios()
    
    // Act
    results = executeAllCombinations(frameworks, allTests)
    
    // Assert
    ASSERT results cover all framework-difficulty combinations
    ASSERT no memory leaks during execution
    ASSERT UI remains responsive throughout
  }
  
  TEST "should maintain consistency across multiple runs" {
    // Arrange
    framework = new LinguisticImperative()
    scenario = getTestScenario("easy-file-creation")
    
    // Act
    results1 = executeScenario(framework, scenario)
    results2 = executeScenario(framework, scenario)
    
    // Assert
    ASSERT results1.toolCalls == results2.toolCalls
    ASSERT results1.metrics == results2.metrics
  }
}
```

### 8.3 Performance and Load Tests

```pseudocode
TEST_SUITE PerformanceTests {
  TEST "should complete all tests within time limit" {
    startTime = getCurrentTime()
    results = executeAllTests()
    endTime = getCurrentTime()
    
    ASSERT (endTime - startTime) < 30000 // 30 seconds
  }
  
  TEST "should maintain memory usage under limit" {
    initialMemory = getMemoryUsage()
    executeAllTests()
    finalMemory = getMemoryUsage()
    
    ASSERT (finalMemory - initialMemory) < 50 * 1024 * 1024 // 50MB
  }
  
  TEST "should handle rapid successive executions" {
    FOR i = 1 TO 10 {
      executeTestRun()
      ASSERT no errors occurred
      ASSERT UI remains responsive
    }
  }
}
```

This specification provides a comprehensive foundation for implementing the LLM experiment environment with clear functional requirements, detailed architecture, and robust testing anchors. Each module is designed to be independently testable and maintainable while staying within the specified constraints.
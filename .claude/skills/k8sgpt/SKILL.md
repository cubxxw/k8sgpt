```markdown
# k8sgpt Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill provides guidance for contributing to the `k8sgpt` repository, a Go codebase focused on Kubernetes analysis. It covers coding conventions, commit patterns, testing strategies, and common development workflows, enabling consistent and efficient collaboration.

## Coding Conventions

### File Naming
- Use **snake_case** for file names.
  - Example: `analyzer_core.go`, `error_handler_test.go`

### Import Style
- Use **relative imports** within the module.
  - Example:
    ```go
    import (
        "fmt"
        "k8sgpt/pkg/analyzer"
    )
    ```

### Export Style
- Use **named exports** for functions, types, and variables.
  - Example:
    ```go
    // Exported function
    func AnalyzePod(pod v1.Pod) error {
        // implementation
    }
    ```

### Commit Messages
- Follow **conventional commit** style.
- Common prefixes: `chore`, `fix`
- Example:
  ```
  fix(analyzer): handle nil pointer in pod analysis
  ```

## Workflows

### Bugfix with Unit Test
**Trigger:** When fixing a bug in an analyzer and ensuring it is covered by a test  
**Command:** `/fix-with-test`

1. Identify and fix the bug in the relevant analyzer implementation file (e.g., `pkg/analyzer/my_analyzer.go`).
2. Add or update a corresponding unit test file (e.g., `pkg/analyzer/my_analyzer_test.go`) to cover the bug or regression.
3. Commit both the implementation and test changes together.

**Example:**
```go
// pkg/analyzer/pod_analyzer.go
func AnalyzePod(pod v1.Pod) error {
    if pod == nil {
        return fmt.Errorf("pod is nil")
    }
    // ...rest of analysis
}
```
```go
// pkg/analyzer/pod_analyzer_test.go
func TestAnalyzePod_NilPod(t *testing.T) {
    err := AnalyzePod(nil)
    if err == nil {
        t.Error("expected error for nil pod")
    }
}
```

### Release Version Bump
**Trigger:** When releasing a new version  
**Command:** `/release`

1. Update the release manifest file (`.release-please-manifest.json`).
2. Update `CHANGELOG.md` with the new release notes.
3. Update `README.md` if necessary.

**Example:**
- Increment version in `.release-please-manifest.json`:
  ```json
  {
    "k8sgpt": "1.2.0"
  }
  ```
- Add release notes to `CHANGELOG.md`:
  ```
  ## [1.2.0] - 2024-06-01
  ### Added
  - New analyzer for pod security policies
  ### Fixed
  - Handle nil pointer in pod analysis
  ```

## Testing Patterns

- Test files use the pattern: `*_test.go`
- Testing framework is not explicitly specified, but standard Go testing is implied.
- Example test:
  ```go
  // pkg/analyzer/error_handler_test.go
  func TestHandleError(t *testing.T) {
      err := HandleError("test error")
      if err == nil {
          t.Error("expected error, got nil")
      }
  }
  ```

## Commands

| Command         | Purpose                                                    |
|-----------------|------------------------------------------------------------|
| /fix-with-test  | Fix a bug and add/update a unit test for the regression    |
| /release        | Bump version, update changelog and documentation for release|
```

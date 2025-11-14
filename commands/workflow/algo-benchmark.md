---
name: algo-benchmark
description: Run comprehensive algorithm benchmarks including time/space complexity analysis, performance profiling, and comparative testing across different implementations.
---

Execute comprehensive benchmarking and performance analysis for algorithm implementations.

## Steps
1. Identify target algorithm(s) to benchmark
2. Set up test cases with varying input sizes
3. Run performance profiling (time and memory)
4. Analyze complexity empirically
5. Compare against theoretical bounds
6. Generate performance report with visualizations

## Benchmark Categories

### 1. Time Complexity Analysis
- Measure execution time across input sizes: n = 10, 100, 1K, 10K, 100K, 1M
- Plot time vs input size
- Fit curve to determine empirical complexity (O(n), O(n log n), O(n²), etc.)
- Compare to theoretical complexity

### 2. Space Complexity Analysis
- Memory profiling using memory_profiler
- Track peak memory usage
- Analyze memory allocation patterns
- Identify memory leaks or inefficiencies

### 3. Comparative Analysis
- Test multiple implementations (naive vs optimized)
- Compare different algorithms for same problem
- Language/library comparisons (pure Python vs NumPy)
- Parallel vs sequential execution

### 4. Edge Cases & Stress Testing
- Empty inputs
- Single element
- Maximum size inputs
- Worst-case scenarios
- Random vs pathological inputs

## Profiling Tools

### Python Profilers
- **cProfile**: Function-level profiling
- **line_profiler**: Line-by-line time analysis
- **memory_profiler**: Memory usage tracking
- **py-spy**: Statistical profiler for production code

### Benchmarking
- **timeit**: Accurate timing of small code snippets
- **pytest-benchmark**: Integrated benchmark tests
- Custom timing harness for comprehensive tests

## Output Report

```markdown
# Algorithm Benchmark Report - [Algorithm Name]

## Summary
- **Algorithm**: [Name and brief description]
- **Theoretical Complexity**: Time O(...), Space O(...)
- **Empirical Complexity**: Time O(...), Space O(...)
- **Date**: [Timestamp]

## Implementation Details
- Language: Python [version]
- Libraries: [list]
- Hardware: [CPU, RAM]

## Performance Results

### Time Complexity
| Input Size | Time (ms) | Time/Element (μs) |
|------------|-----------|-------------------|
| 10         | X.XX      | X.XX              |
| 100        | X.XX      | X.XX              |
| 1,000      | X.XX      | X.XX              |
| 10,000     | X.XX      | X.XX              |
| 100,000    | X.XX      | X.XX              |

**Empirical Complexity**: O(...)
**Growth Rate**: [Linear/Quadratic/etc.]

### Space Complexity
| Input Size | Memory (MB) | Memory/Element (bytes) |
|------------|-------------|------------------------|
| ...        | ...         | ...                    |

### Comparative Analysis
[If comparing multiple implementations]

| Implementation | Time (n=10K) | Memory (n=10K) | Notes |
|----------------|--------------|----------------|-------|
| Naive          | X.XX ms      | X.XX MB        | ...   |
| Optimized      | X.XX ms      | X.XX MB        | ...   |
| NumPy          | X.XX ms      | X.XX MB        | ...   |

**Speedup**: Optimized is XXx faster than naive

## Profiling Details

### Hotspots (top functions by time)
1. [function_name]: XX% of total time
2. [function_name]: XX% of total time

### Memory Hotspots
[Memory-intensive operations]

## Visualizations
- Time vs Input Size (log-log plot)
- Memory vs Input Size
- Performance comparison charts

## Recommendations
- [Optimization suggestion 1]
- [Optimization suggestion 2]
- [Trade-off considerations]

## Test Cases
- Total test cases: X
- Edge cases tested: X
- Correctness: All passed ✓

## Bottleneck Analysis
[Identified bottlenecks and proposed solutions]
```

## Visualization
Generate plots using matplotlib:
- Time complexity curves
- Memory usage over time
- Comparison bar charts
- Scaling behavior (log-log plots)

## Usage Examples
- `/algo-benchmark my_sort.py` - Benchmark specific file
- `/algo-benchmark --function quick_sort` - Benchmark function
- `/algo-benchmark --compare "bubble_sort,merge_sort,quick_sort"` - Compare algorithms
- `/algo-benchmark --max-size 1000000` - Test up to 1M elements
- `/algo-benchmark --profile memory` - Focus on memory profiling

## Integration
- Save reports to `benchmarks/` directory
- Version control benchmark results
- Track performance over time
- Generate regression alerts

Make data-driven optimization decisions based on empirical evidence.

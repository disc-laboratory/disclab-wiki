# Evaluation Metrics

Choose metrics that match the engineering objective.

## Common metrics

- **mAP**: useful for detection and segmentation benchmarks
- **IoU / mIoU**: useful for overlap-based segmentation quality
- **precision / recall / F1**: useful when false negatives or false positives matter differently
- **pixel accuracy**: only supplementary for imbalanced segmentation tasks

## Engineering note

For damage tasks, report not only aggregate metrics but also:
- per-class metrics
- class imbalance discussion
- qualitative examples
- failure modes relevant to field use


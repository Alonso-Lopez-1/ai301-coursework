The failure comes from `test_readme_with_all_quality_signals`, not from the README scorer itself. The scorer correctly treats 500 or more words as `comprehensive`, but the test fixture only contains about 51 words while still expecting that category. My plan is to update the fixture so it is actually long enough to represent a comprehensive README and change the word-count assertion from `> 100` to `>= 500`.

I only expect to change `tests/unit/test_readme_scorer.py`. I am not planning to change the scorer thresholds, the word-count logic, or any unrelated tests. I also do not plan to add a separate exact-boundary test for 500 words as part of this issue.

I will expand the existing README fixture while keeping the quality signals it already tests, such as installation, usage, tech stack, badges, and demo content. I will keep the existing `word_count_category == "comprehensive"` assertion so the test still verifies both the count and the category.

To verify the change, I will re-run:

`pytest tests/unit/test_readme_scorer.py -q`

Before the fix, `test_readme_with_all_quality_signals` fails because the fixture only produces about 51 words. After the change, I expect the fixture to produce at least 500 words, the `word_count >= 500` assertion to pass, and the category to remain `comprehensive`. The rest of the README scorer tests should continue to pass.

The main thing I want to avoid is accidentally changing one of the other quality signals in the fixture while expanding it. If the test still fails after the fixture is over the threshold, I would investigate that result before changing the production scorer.

## Deviations

[What changed between the plan you posted and the change you built, and
why. If nothing changed, say so in your own words - "nothing changed;
the plan held" earns these points in full. Leaving this blank does not.]

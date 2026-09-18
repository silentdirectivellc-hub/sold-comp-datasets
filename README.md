# Sold-comp datasets for resale pricing

Open, dated datasets of **completed sale prices** for items that show up constantly in estate sales,
coin roll hunts, thrift runs and consignment intake. Asking prices are opinions; these are closes.

Every row here was pulled from completed listings and reduced to a price **per unit**, so a lot of 40
coins and a single coin can sit in the same table. Spot prices are fetched live at the timestamp in
the file, never quoted from memory.

Maintained by [Silent Directive](https://flipworth.silentdirectivellc.com/?src=github-soldcomps).
Issues and pull requests with additional comps are welcome.

---

## Dataset 1 - 35% silver "war" nickels (1942-1945), 90 days, n=45

Collected 2026-09-18. Two searches: `1942 P war nickel` (n=25) and `war nickels lot 35% silver` (n=20).
Raw rows: [`data/war-nickels-2026-09-18.csv`](data/war-nickels-2026-09-18.csv).

**Melt, computed not quoted:** 5.00 g at .350 fine = 1.75 g fine = **0.0563 ozt** per coin.
Silver **$66.918/ozt** at 2026-09-18T06:46:08Z (cross-checked against front-month futures at $67.235,
0.5% apart) = **$3.77 of silver per coin**, about 75x face value.

| how it sold | per-coin closes | median |
|---|---|---|
| single, raw, circulated | 3.25, 3.78, 4.00, 4.45, 4.75, 4.75, 4.94, 5.94 | **$4.60** |
| lot of 3 to 6, fixed price | 3.60, 3.60, 3.70, 4.65, 5.50 | **$3.70** |
| lot of 10 to 100, fixed price | 1.78, 3.00, 3.03, 3.06, 3.25, 3.37 | **$3.05** |
| lot of 10 to 100, auction | 2.42, 2.80, 2.85, 2.90, 3.00, 3.00 | **$2.88** |

### What the numbers say

1. **Lot size is a discount, and past ~10 coins it cuts through melt.** The ladder is monotonic and
   melt sits *inside* it: singles $4.60 > melt $3.77 > small lots $3.70 > big fixed lots $3.05 >
   big auction lots $2.88. After the ~13.25% marketplace fee and postage, a 20-coin auction lot nets
   roughly **$2.20 a coin, about 58% of melt** - close to what a counter offers when it takes on the
   photographing, packing and waiting.
2. **No 1942-P date premium in circulated grades.** Random-date circulated singles closed $4.45 and
   $4.75 while dated 1942-P examples closed in the same band. The mint mark matters to a collector
   of the series, not to the melt buyer who sets the floor.
3. **The one real exception is the 1942-P proof** (27,600 struck), which closed at $169.90. Proof
   status, not date, is what breaks a coin out of the metal price.

### Caveats, stated up front

90-day window; bucket sizes are small (5 to 8 closes each); closing price is not seller net (fees and
postage come out after); condition is as described by the seller, not graded. Treat the medians as a
band, not a quote.

---

## Method (reusable for any category)

1. Search **completed** listings only, then filter to sold.
2. Reduce every close to a price **per unit** so lots and singles are comparable.
3. Bucket by *how it sold* (single / small lot / large lot, fixed price / auction), because the
   selling format moves the price more than small condition differences do.
4. For anything with metal content, compute the **melt floor live** from weight x fineness x spot,
   and check where the floor sits inside the ladder. A floor is a number nobody in a forum thread
   will produce for you.
5. Take medians, not averages; publish the bucket size next to the median.

## Related write-ups

Longer, plain-English versions of this method, by category:

- [How to price estate sale items](https://flipworth.silentdirectivellc.com/guides/how-to-price-estate-sale-items?src=github-soldcomps)
- [What is my vintage item worth?](https://flipworth.silentdirectivellc.com/guides/what-is-my-vintage-item-worth?src=github-soldcomps)
- [Are old coins worth anything?](https://flipworth.silentdirectivellc.com/guides/are-old-coins-worth-anything?src=github-soldcomps)
- [Sterling silver flatware value](https://flipworth.silentdirectivellc.com/guides/sterling-silver-flatware-value?src=github-soldcomps)
- [Is it worth reselling?](https://flipworth.silentdirectivellc.com/guides/is-it-worth-reselling?src=github-soldcomps)

If you would rather not do the arithmetic by hand on a table full of items, the same sold-comp lookup
runs from a photo in [FlipWorth](https://flipworth.silentdirectivellc.com/?src=github-soldcomps).

## License

Data released under [CC0 1.0](LICENSE) - public domain. Use it, quote it, no attribution required.

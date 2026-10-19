```javascript
function dailyLog206() {
  const reviews = [
    { customer: "Customer 1", rating: 5, comment: "Excellent service" },
    { customer: "Customer 2", rating: 4, comment: "Very helpful" },
    { customer: "Customer 3", rating: 2, comment: "Slow delivery" },
    { customer: "Customer 4", rating: 5, comment: "Amazing experience" },
    { customer: "Customer 5", rating: 3, comment: "Could be better" },
  ];

  const totalRating = reviews.reduce(
    (sum, review) => sum + review.rating,
    0
  );

  const averageRating = totalRating / reviews.length;

  const positive = reviews.filter(
    review => review.rating >= 4
  );

  const negative = reviews.filter(
    review => review.rating <= 2
  );

  console.log("=== Customer Satisfaction Report ===");
  console.log(`Total Reviews: ${reviews.length}`);
  console.log(`Average Rating: ${averageRating.toFixed(1)}/5`);
  console.log(
    `Positive Reviews: ${positive.length} (${(
      positive.length / reviews.length * 100
    ).toFixed(0)}%)`
  );
  console.log(`Negative Reviews: ${negative.length}`);

  console.log("\n=== Feedback Requiring Attention ===");

  negative.forEach(review => {
    console.log(`⚠️ ${review.comment}`);
  });

  console.log(
    averageRating >= 4
      ? "\n✅ Customer satisfaction is high!"
      : "\n🔧 Consider improving the customer experience."
  );
}

dailyLog206();
```

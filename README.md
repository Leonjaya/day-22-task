# day-22-task
import React from 'react';

const pricingPlans = [
  {
    title: "FREE",
    price: "$0/month",
    features: [
      "Single User",
      "50GB Storage",
      "Unlimited Public Projects",
      "Community Access",
      "Unlimited Private Projects",
      "Dedicated Phone Support",
      "Free Subdomain",
      "Monthly Status Reports"
    ],
    available: [true, true, true, true, false, false, false, false]
  },
  {
    title: "PLUS",
    price: "$9/month",
    features: [
      "5 Users",
      "50GB Storage",
      "Unlimited Public Projects",
      "Community Access",
      "Unlimited Private Projects",
      "Dedicated Phone Support",
      "Free Subdomain",
      "Monthly Status Reports"
    ],
    available: [true, true, true, true, true, true, true, false]
  },
  {
    title: "PRO",
    price: "$49/month",
    features: [
      "Unlimited Users",
      "50GB Storage",
      "Unlimited Public Projects",
      "Community Access",
      "Unlimited Private Projects",
      "Dedicated Phone Support",
      "Free Subdomain",
      "Monthly Status Reports"
    ],
    available: [true, true, true, true, true, true, true, true]
  }
];

const PricingCard = ({ title, price, features, available }) => (
  <div className="card">
    <h2>{title}</h2>
    <h3>{price}</h3>
    <ul>
      {features.map((feature, index) => (
        <li key={index} style={{ color: available[index] ? 'black' : 'grey' }}>
          {available[index] ? '✔️' : '❌'} {feature}
        </li>
      ))}
    </ul>
    <button>BUTTON</button>
  </div>
);

const PricingCards = () => (
  <div className="pricing-cards">
    {pricingPlans.map((plan, index) => (
      <PricingCard
        key={index}
        title={plan.title}
        price={plan.price}
        features={plan.features}
        available={plan.available}
      />
    ))}
  </div>
);

export default PricingCards;

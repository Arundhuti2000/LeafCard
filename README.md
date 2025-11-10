# LeafCart - Sustainability Dashboard

A comprehensive sustainability tracking platform that helps users make eco-friendly shopping decisions by analyzing their purchase history across multiple merchants.

## 🌟 Features

### 1. **Merchant Management System**

- **Connect/Disconnect Merchants**: Dedicated UI for managing merchant connections
- **40+ Supported Merchants**: Including Amazon, Walmart, Target, DoorDash, Uber Eats, and more
- **Sustainability Ratings**: Each merchant has a 1-5 star rating based on environmental impact:
  - ⭐⭐⭐⭐⭐ **Great**: 100% sustainable materials with certifications
  - ⭐⭐⭐⭐ **Pretty Good**: Majority sustainable/recycled materials
  - ⭐⭐⭐ **It's a Start**: Some sustainable effort
  - ⭐⭐ **Some Problems**: Minimal sustainability efforts
  - ⭐ **Avoid**: Non-renewable, non-recyclable materials

### 2. **Transaction Tracking**

- View all transactions from connected merchants
- Expandable transaction details with product lists
- Show 10 transactions initially, load more in batches of 10
- Filter and search capabilities
- Sustainability scoring for each transaction

### 3. **AI Chat Assistant**

- Floating chat widget for sustainability queries
- Get advice on eco-friendly alternatives
- Learn about product sustainability ratings
- Ask questions about your purchase history
- Customizable and extensible for any AI backend

### 4. **Dashboard Analytics**

- Overall sustainability score (0-100)
- Total spending across all connected merchants
- Transaction count tracking
- Visual indicators with color-coded ratings
- Real-time updates when merchants are connected/disconnected

## 🎨 Design Features

- **Dark Theme**: Modern zinc-950 background with emerald accents
- **Color-Coded Ratings**: Gradient colors from green (sustainable) to red (avoid)
- **Brand Icons**: Authentic company logos using react-icons
- **Smooth Animations**: Modern transitions without bouncy effects
- **Responsive Layout**: Works on desktop, tablet, and mobile

## 🔧 Technical Stack

- **Framework**: Next.js 16 with App Router
- **Styling**: Tailwind CSS v4
- **Icons**: Lucide React + React Icons
- **TypeScript**: Full type safety
- **API Integration**: Knot API for merchant data

## 📁 Project Structure

```
frontend/
├── app/
│   ├── page.tsx              # Landing page
│   └── dashboard/
│       └── page.tsx          # Dashboard page
├── components/
│   ├── landing-page.tsx      # Landing page component
│   ├── merchant-dashboard.tsx # Main dashboard
│   ├── connect-merchants-modal.tsx # Merchant connection UI
│   └── ai-chat-widget.tsx    # AI chat interface
├── lib/
│   ├── api.ts                # Knot API configuration
│   ├── merchantData.ts       # Transaction data handling
│   └── merchantRatings.ts    # Sustainability ratings
└── public/
    └── api-sample-responses/ # Sample transaction data
```

## 🚀 Getting Started

### Prerequisites

- Node.js 18+ installed
- Knot API credentials (client_id and secret)

### Installation

1. Clone the repository:

```bash
git clone <repository-url>
cd Leafcart/frontend
```

2. Install dependencies:

```bash
npm install
```

3. Configure environment variables:

```bash
cp .env.example .env.local
```

4. Edit `.env.local` with your Knot API credentials:

```env
NEXT_PUBLIC_KNOT_CLIENT_ID=your_client_id_here
NEXT_PUBLIC_KNOT_SECRET=your_secret_here
```

5. Run the development server:

```bash
npm run dev
```

6. Open [http://localhost:3000](http://localhost:3000) in your browser

## 🔌 API Configuration

### Knot API Setup

The application uses the Knot API for fetching merchant transactions. Configuration is in `lib/api.ts`:

```typescript
export const API_CONFIG = {
  baseUrl: "https://development.knotapi.com",
  endpoints: {
    transactionSync: "/transactions/sync",
    merchantList: "/merchant/list",
    accountsGet: "/accounts",
    // ... more endpoints
  },
};
```

### Available API Functions

```typescript
// Fetch available merchants
await fetchMerchantList({
  type: "transaction_link",
  platform: "web",
  external_user_id: "user_123",
});

// Sync transactions for a merchant
await syncTransactions({
  merchant_id: 44,
  external_user_id: "user_123",
  limit: 100,
});

// Get connected accounts
await getAccounts({
  external_user_id: "user_123",
});
```

## 🎯 Key Components

### Connect Merchants Modal

- Search and filter merchants
- Filter by sustainability rating (1-5 stars)
- Visual rating indicators with color gradients
- View more button for pagination
- Toggle connections on/off

### AI Chat Widget

- Floating chat button in bottom-right
- Minimizable chat interface
- Message history
- Typing indicators
- Customizable AI responses

### Dashboard

- Dynamic stats based on connected merchants
- Expandable merchant cards
- Transaction details with product lists
- Sustainability scoring
- Color-coded indicators

## 📊 Sustainability Scoring

### Product-Level Scoring

Products are scored based on:

- Sustainable materials (organic, recycled, bamboo)
- Certifications (GOTS, FSC, Rainforest Alliance)
- Biodegradability
- Durability and quality
- Packaging sustainability

### Transaction Scoring

Each transaction receives a score (0-100) based on:

- Presence of sustainable keywords in product names
- Avoidance of single-use plastics
- Eco-friendly product categories

### Merchant Ratings

Merchants are rated 1-5 stars based on:

- Corporate sustainability commitments
- Material sourcing practices
- Environmental certifications
- Packaging policies
- Carbon footprint initiatives

## 🔮 Future Enhancements

- [ ] Real-time AI chat integration (OpenAI, Anthropic, etc.)
- [ ] Export sustainability reports
- [ ] Set sustainability goals and track progress
- [ ] Product recommendations based on preferences
- [ ] Social features (share achievements, compare with friends)
- [ ] Push notifications for sustainable deals
- [ ] Integration with more merchant APIs
- [ ] Carbon footprint calculator
- [ ] Rewards program for sustainable choices

## 📝 Environment Variables

| Variable                     | Description                  | Required |
| ---------------------------- | ---------------------------- | -------- |
| `NEXT_PUBLIC_KNOT_CLIENT_ID` | Knot API client ID           | Yes      |
| `NEXT_PUBLIC_KNOT_SECRET`    | Knot API secret key          | Yes      |
| `NEXT_PUBLIC_USE_MOCK_DATA`  | Use mock data instead of API | No       |

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📄 License

This project is licensed under the MIT License.

## 🙏 Acknowledgments

- Knot API for merchant integrations
- Lucide React for beautiful icons
- Tailwind CSS for styling utilities
- Next.js team for the framework

## 📞 Support

For questions or issues, please open an issue on GitHub or contact the development team.

---

Built for a more sustainable future

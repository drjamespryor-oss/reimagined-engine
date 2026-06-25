# reimagined-engine
Interface defining the intraday market performance metrics for a stock
CUSIP/ISIN properties
// Interface defining the regulatory identifiers for a security
interface SecurityIdentifiers {
  ticker: string;
  companyName: string;
  cusip: string; // 9-character North American identifier
  isin: string;  // 12-character International Securities Identification Number
}

// Collection of regulatory identifier data for the specified equities
const equityIdentifiers: Record<string, SecurityIdentifiers> = {
  KBH: {
    ticker: "KBH",
    companyName: "KB Home",
    cusip: "48666K109",
    isin: "US48666K1097"
  },
  ABSI: {
    ticker: "ABSI",
    companyName: "Absci Corp",
    cusip: "00091E109",
    isin: "US00091E1091"
  },
  WEN: {
    ticker: "WEN",
    companyName: "Wendy's Company",
    cusip: "95058W100",
    isin: "US95058W1009"
  },
  COUR: {
    ticker: "COUR",
    companyName: "Coursera, Inc.",
    cusip: "22266M104",
    isin: "US22266M1045"
  },
  BLDR: {
    ticker: "BLDR",
    companyName: "Builders FirstSource, Inc.",
    cusip: "12008R107",
    isin: "US12008R1079"
  }
};

// Example validation helper to verify identifier lengths before processing trades
function validateIdentifiers(identifiers: SecurityIdentifiers): boolean {
  const isCusipValid = identifiers.cusip.length === 9;
  const isIsinValid = identifiers.isin.length === 12;
  return isCusipValid && isIsinValid;
}

// Demonstrate validation loop
Object.values(equityIdentifiers).forEach(security => {
  const isValid = validateIdentifiers(security);
  console.log(`Security: ${security.ticker} | Valid Identifiers: ${isValid}`);
});

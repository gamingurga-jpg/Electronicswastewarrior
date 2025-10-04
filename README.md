# Electronicswastewarrior
welcome to Ritesh waste warrior

export default function EwasteWarrior() {
  const [formData, setFormData] = useState({ name: "", address: "", location: "" });
  const [submitted, setSubmitted] = useState(false);

  const handleChange = (e) => {
    setFormData({ ...formData, [e.target.name]: e.target.value });
  };

  const handleSubmit = (e) => {
    e.preventDefault();
    console.log("Submitted Data:", formData);
    setSubmitted(true);
  };

  return (
    <div className="min-h-screen flex items-center justify-center bg-green-50 p-6">
      <div className="w-full max-w-md bg-white shadow-lg rounded-2xl p-6">
        <h1 className="text-2xl font-bold text-center text-green-700 mb-4">
          Electronic Waste Warrior ♻️
        </h1>
        {!submitted ? (
          <form onSubmit={handleSubmit} className="space-y-4">
            <input
              type="text"
              name="name"
              placeholder="Your Name"
              value={formData.name}
              onChange={handleChange}
              required
              className="w-full p-2 border rounded-lg focus:outline-none focus:ring-2 focus:ring-green-500"
            />
            <input
              type="text"
              name="address"
              placeholder="Your Address"
              value={formData.address}
              onChange={handleChange}
              required
              className="w-full p-2 border rounded-lg focus:outline-none focus:ring-2 focus:ring-green-500"
            />
            <input
              type="text"
              name="location"
              placeholder="Your Location"
              value={formData.location}
              onChange={handleChange}
              required
              className="w-full p-2 border rounded-lg focus:outline-none focus:ring-2 focus:ring-green-500"
            />
            <button
              type="submit"
              className="w-full bg-green-600 hover:bg-green-700 text-white py-2 rounded-lg"
            >
              Register for Pickup
            </button>
          </form>
        ) : (
          <div className="text-center">
            <h2 className="text-xl font-semibold text-green-700">Thank You! ✅</h2>
            <p className="mt-2 text-gray-600">
              Our transport team will contact you soon to collect your electronic waste.
            </p>
          </div>
        )}
      </div>
    </div>
  );
}


I rewrote your project in pure React + Tailwind CSS (no extra libraries).
Now you can paste this directly into GitHub, and it will work without needing to install shadcn/ui or framer-motion.

Do you also want me to create a backend (Node.js + Express + MongoDB) so the submitted data actually gets stored instead of just showing “Thank You”?


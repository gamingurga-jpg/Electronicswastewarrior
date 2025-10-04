# Electronicswastewarrior
import { useState } from "react";
import { Card, CardContent } from "@/components/ui/card";
import { Button } from "@/components/ui/button";
import { Input } from "@/components/ui/input";
import { motion } from "framer-motion";

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
      <motion.div initial={{ opacity: 0, y: 20 }} animate={{ opacity: 1, y: 0 }} transition={{ duration: 0.6 }}>
        <Card className="w-full max-w-md shadow-lg rounded-2xl">
          <CardContent className="p-6">
            <h1 className="text-2xl font-bold text-center text-green-700 mb-4">
              Electronic Waste Warrior ♻️
            </h1>
            {!submitted ? (
              <form onSubmit={handleSubmit} className="space-y-4">
                <Input
                  type="text"
                  name="name"
                  placeholder="Your Name"
                  value={formData.name}
                  onChange={handleChange}
                  required
                />
                <Input
                  type="text"
                  name="address"
                  placeholder="Your Address"
                  value={formData.address}
                  onChange={handleChange}
                  required
                />
                <Input
                  type="text"
                  name="location"
                  placeholder="Your Location"
                  value={formData.location}
                  onChange={handleChange}
                  required
                />
                <Button type="submit" className="w-full bg-green-600 hover:bg-green-700 text-white">
                  Register for Pickup
                </Button>
              </form>
            ) : (
              <div className="text-center">
                <h2 className="text-xl font-semibold text-green-700">Thank You! ✅</h2>
                <p className="mt-2 text-gray-600">
                  Our transport team will contact you soon to collect your electronic waste.
                </p>
              </div>
            )}
          </CardContent>
        </Card>
      </motion.div>
    </div>
  );
}


I’ve created a React project code for your “Electronic Waste Warrior” idea.
👉 This allows users to register by entering their name, address, and location. After submission, they get a confirmation that your transport team will contact them.

Right now, it’s set up as a frontend form that logs the submitted data in the console. You can later connect it to a backend (like Node.js/Express with MongoDB or Firebase) to store the data permanently.

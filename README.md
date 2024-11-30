- 👋 Hi, I’m @rehman8809
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
rehman8809/rehman8809 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
import React from 'react';
import { Mail, Phone, MapPin } from 'lucide-react';
import { contactInfo } from '../config/contact';

export function Contact() {
  return (
    <section id="contact" className="relative bg-white py-20">
      <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div className="text-center">
          <h2 className="text-3xl font-extrabold text-gray-900 sm:text-4xl">
            Contact Us
          </h2>
          <p className="mt-4 text-lg text-gray-500">
            Get in touch with our expert consultants
          </p>
        </div>

        <div className="mt-20 grid grid-cols-1 md:grid-cols-2 gap-10">
          <div className="bg-gray-50 rounded-lg p-8">
            <form className="space-y-6">
              <div>
                <label htmlFor="name" className="block text-sm font-medium text-gray-700">
                  Full Name
                </label>
                <input
                  type="text"
                  name="name"
                  id="name"
                  className="mt-1 block w-full rounded-md border-gray-300 shadow-sm focus:border-blue-500 focus:ring-blue-500"
                />
              </div>
              <div>
                <label htmlFor="email" className="block text-sm font-medium text-gray-700">
                  Email
                </label>
                <input
                  type="email"
                  name="email"
                  id="email"
                  className="mt-1 block w-full rounded-md border-gray-300 shadow-sm focus:border-blue-500 focus:ring-blue-500"
                />
              </div>
              <div>
                <label htmlFor="message" className="block text-sm font-medium text-gray-700">
                  Message
                </label>
                <textarea
                  id="message"
                  name="message"
                  rows={4}
                  className="mt-1 block w-full rounded-md border-gray-300 shadow-sm focus:border-blue-500 focus:ring-blue-500"
                />
              </div>
              <div>
                <button
                  type="submit"
                  className="w-full flex justify-center py-2 px-4 border border-transparent rounded-md shadow-sm text-sm font-medium text-white bg-blue-600 hover:bg-blue-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-blue-500"
                >
                  Send Message
                </button>
              </div>
            </form>
          </div>

          <div className="space-y-8">
            <div className="flex items-start">
              <Mail className="h-6 w-6 text-blue-600 mt-1" />
              <div className="ml-4">
                <h4 className="text-lg font-medium text-gray-900">Email</h4>
                <p className="mt-1 text-gray-500">{contactInfo.email}</p>
              </div>
            </div>

            <div className="flex items-start">
              <Phone className="h-6 w-6 text-blue-600 mt-1" />
              <div className="ml-4">
                <h4 className="text-lg font-medium text-gray-900">Phone Numbers</h4>
                {contactInfo.phones.map((phone, index) => (
                  <p key={index} className="mt-1 text-gray-500">
                    {phone.country}: {phone.number}
                  </p>
                ))}
              </div>
            </div>

            <div className="flex items-start">
              <MapPin className="h-6 w-6 text-blue-600 mt-1" />
              <div className="ml-4">
                <h4 className="text-lg font-medium text-gray-900">Office</h4>
                <p className="mt-1 text-gray-500">
                  {contactInfo.address.building}<br />
                  {contactInfo.address.street}<br />
                  {contactInfo.address.city}, {contactInfo.address.country}
                </p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
  );
}

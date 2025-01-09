import React from 'react';
import { Github, Linkedin, Mail, Monitor, Database, Tool } from 'lucide-react';

const ProfileCard = () => {
  const personalInfo = {
    name: "Nishan Dananjaya",
    role: "EEE Undergraduate",
    focus: ["Embedded Systems", "AI/ML"],
    currentlyLearning: "IoT & Robotics",
    funFact: "Memory like a goldfish 🐠"
  };

  const skills = {
    languages: ["Python", "C++"],
    frameworks: ["TensorFlow", "PyTorch"],
    tools: ["Arduino", "RaspberryPi"],
    interests: ["Smart Systems", "ML Applications"]
  };

  const Badge = ({ text, color = "blue" }) => (
    <span className={`inline-flex items-center px-3 py-1 rounded-full text-sm font-medium bg-${color}-100 text-${color}-800 mr-2 mb-2`}>
      {text}
    </span>
  );

  const Section = ({ title, icon, children }) => (
    <div className="mb-8">
      <div className="flex items-center mb-4">
        {icon}
        <h2 className="text-xl font-bold ml-2">{title}</h2>
      </div>
      {children}
    </div>
  );

  return (
    <div className="max-w-4xl mx-auto p-6 bg-gray-50 rounded-lg shadow-lg">
      {/* Header */}
      <div className="text-center mb-8">
        <h1 className="text-4xl font-bold mb-4">{personalInfo.name}</h1>
        <div className="flex justify-center space-x-4 mb-6">
          <a href="https://linkedin.com/in/nishandananjayab" className="text-blue-600 hover:text-blue-800">
            <Linkedin className="w-6 h-6" />
          </a>
          <a href="https://github.com/NishDananjaya" className="text-gray-800 hover:text-gray-600">
            <Github className="w-6 h-6" />
          </a>
          <a href="mailto:your-email@example.com" className="text-red-600 hover:text-red-800">
            <Mail className="w-6 h-6" />
          </a>
        </div>
      </div>

      {/* About Section */}
      <Section title="About Me" icon={<Monitor className="w-5 h-5" />}>
        <div className="grid grid-cols-1 md:grid-cols-2 gap-4 bg-white p-4 rounded-lg">
          <div>
            <p className="mb-2"><span className="font-semibold">Role:</span> {personalInfo.role}</p>
            <p className="mb-2"><span className="font-semibold">Focus:</span> {personalInfo.focus.join(", ")}</p>
          </div>
          <div>
            <p className="mb-2"><span className="font-semibold">Learning:</span> {personalInfo.currentlyLearning}</p>
            <p><span className="font-semibold">Fun Fact:</span> {personalInfo.funFact}</p>
          </div>
        </div>
      </Section>

      {/* Skills Section */}
      <Section title="Tech Stack" icon={<Database className="w-5 h-5" />}>
        <div className="space-y-4">
          <div>
            <h3 className="font-semibold mb-2">Languages & Frameworks</h3>
            <div className="flex flex-wrap">
              {[...skills.languages, ...skills.frameworks].map((skill, index) => (
                <Badge key={index} text={skill} />
              ))}
            </div>
          </div>
          <div>
            <h3 className="font-semibold mb-2">Tools & Interests</h3>
            <div className="flex flex-wrap">
              {[...skills.tools, ...skills.interests].map((item, index) => (
                <Badge key={index} text={item} color="green" />
              ))}
            </div>
          </div>
        </div>
      </Section>

      {/* Projects Section */}
      <Section title="Featured Projects" icon={<Tool className="w-5 h-5" />}>
        <div className="grid grid-cols-1 md:grid-cols-2 gap-4">
          <div className="bg-white p-4 rounded-lg shadow">
            <h3 className="font-bold mb-2">MCQ Generator</h3>
            <p className="text-sm text-gray-600">An AI-powered multiple choice question generator</p>
          </div>
          <div className="bg-white p-4 rounded-lg shadow">
            <h3 className="font-bold mb-2">Gemini Chatbot</h3>
            <p className="text-sm text-gray-600">Sinhala language chatbot using Gemini AI</p>
          </div>
        </div>
      </Section>
    </div>
  );
};

export default ProfileCard;

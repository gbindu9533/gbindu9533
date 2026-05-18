import { motion } from "framer-motion";
import { Github, Linkedin, Mail, MapPin, ExternalLink } from "lucide-react";

export default function GitHubDashboard() {
  // =========================
  // EDIT YOUR DETAILS HERE
  // =========================
  const profile = {
    name: "Sairaj Moulasab Nadaf",
    title: "Full Stack & Web3 Developer",
    subtitle: "Building scalable Web2 & Web3 applications",
    location: "Gadag, Karnataka, India",
    email: "sairaj.nadaf@gmail.com",
    github: "https://github.com/SairajMN",
    linkedin: "https://www.linkedin.com/in/sairaj-m-n/",
    twitter: "https://x.com/sairaj_18",
    bio: "Passionate Full Stack and Blockchain Developer focused on smart contracts, decentralized applications, cybersecurity, and modern UI experiences.",

    stats: [
      { label: "Repositories", value: "25+" },
      { label: "GitHub Streak", value: "100+" },
      { label: "Hackathons", value: "10+" },
      { label: "Technologies", value: "15+" }
    ],

    skills: [
      "React",
      "Node.js",
      "Solidity",
      "TypeScript",
      "MySQL",
      "Tailwind CSS",
      "Foundry",
      "Hardhat",
      "Docker",
      "Python",
      "Git",
      "Web3"
    ],

    projects: [
      {
        title: "DeFiFlow",
        description: "DeFi simulation platform with staking and liquidity features.",
        link: "https://github.com/SairajMN/DeFiFlow"
      },
      {
        title: "AutoCrowd",
        description: "ETHGlobal hackathon project for decentralized crowdfunding.",
        link: "https://github.com/SairajMN/AutoCrowd"
      },
      {
        title: "SMARTCONTRACT-Development",
        description: "Learning and testing Solidity smart contracts using Foundry.",
        link: "https://github.com/SairajMN/SMARTCONTRACT-Development"
      }
    ]
  };

  return (
    <div className="min-h-screen bg-black text-white overflow-hidden relative">
      {/* Animated Background */}
      <div className="absolute inset-0 overflow-hidden">
        <motion.div
          animate={{
            x: [0, 80, 0],
            y: [0, 50, 0]
          }}
          transition={{ duration: 8, repeat: Infinity }}
          className="absolute top-10 left-10 w-96 h-96 bg-purple-500/30 rounded-full blur-3xl"
        />

        <motion.div
          animate={{
            x: [0, -70, 0],
            y: [0, -50, 0]
          }}
          transition={{ duration: 10, repeat: Infinity }}
          className="absolute bottom-10 right-10 w-96 h-96 bg-cyan-500/30 rounded-full blur-3xl"
        />
      </div>

      <div className="relative z-10 max-w-7xl mx-auto px-6 py-10">
        {/* HERO SECTION */}
        <motion.div
          initial={{ opacity: 0, y: 50 }}
          animate={{ opacity: 1, y: 0 }}
          transition={{ duration: 1 }}
          className="text-center"
        >
          <motion.div
            animate={{ rotate: 360 }}
            transition={{ duration: 20, repeat: Infinity, ease: "linear" }}
            className="mx-auto mb-6 w-36 h-36 rounded-full p-1 bg-gradient-to-r from-purple-500 via-cyan-500 to-pink-500"
          >
            <img
              src="https://avatars.githubusercontent.com/u/9919?s=200&v=4"
              alt="profile"
              className="w-full h-full rounded-full object-cover border-4 border-black"
            />
          </motion.div>

          <motion.h1
            initial={{ opacity: 0 }}
            animate={{ opacity: 1 }}
            transition={{ delay: 0.5 }}
            className="text-5xl md:text-7xl font-extrabold bg-gradient-to-r from-purple-400 via-cyan-300 to-pink-400 text-transparent bg-clip-text"
          >
            {profile.name}
          </motion.h1>

          <p className="mt-4 text-2xl text-gray-300">{profile.title}</p>
          <p className="mt-2 text-gray-400">{profile.subtitle}</p>

          <div className="flex justify-center items-center gap-2 mt-4 text-gray-400">
            <MapPin size={18} />
            {profile.location}
          </div>

          {/* Buttons */}
          <div className="flex flex-wrap justify-center gap-4 mt-8">
            <a
              href={profile.github}
              target="_blank"
              className="px-6 py-3 rounded-2xl bg-gradient-to-r from-purple-500 to-pink-500 hover:scale-105 transition duration-300 shadow-lg"
            >
              GitHub
            </a>

            <a
              href={profile.linkedin}
              target="_blank"
              className="px-6 py-3 rounded-2xl border border-white/30 hover:bg-white hover:text-black transition duration-300"
            >
              LinkedIn
            </a>
          </div>
        </motion.div>

        {/* STATS */}
        <div className="grid md:grid-cols-4 gap-6 mt-16">
          {profile.stats.map((item, index) => (
            <motion.div
              key={index}
              whileHover={{ scale: 1.05, y: -10 }}
              className="bg-white/10 border border-white/10 backdrop-blur-xl rounded-3xl p-8 text-center shadow-2xl"
            >
              <h2 className="text-4xl font-bold text-purple-400">
                {item.value}
              </h2>
              <p className="mt-3 text-gray-300">{item.label}</p>
            </motion.div>
          ))}
        </div>

        {/* ABOUT */}
        <motion.div
          initial={{ opacity: 0, y: 40 }}
          whileInView={{ opacity: 1, y: 0 }}
          transition={{ duration: 1 }}
          className="mt-20 bg-white/10 border border-white/10 backdrop-blur-xl rounded-[40px] p-10 shadow-2xl"
        >
          <h2 className="text-4xl font-bold mb-6">About Me</h2>

          <p className="text-gray-300 text-lg leading-8">
            {profile.bio}
          </p>

          <div className="flex flex-wrap gap-4 mt-8">
            <a
              href={`mailto:${profile.email}`}
              className="flex items-center gap-2 px-5 py-3 rounded-2xl bg-purple-500/20 hover:bg-purple-500/40 transition"
            >
              <Mail size={18} />
              Email
            </a>

            <a
              href={profile.github}
              target="_blank"
              className="flex items-center gap-2 px-5 py-3 rounded-2xl bg-cyan-500/20 hover:bg-cyan-500/40 transition"
            >
              <Github size={18} />
              GitHub
            </a>

            <a
              href={profile.linkedin}
              target="_blank"
              className="flex items-center gap-2 px-5 py-3 rounded-2xl bg-pink-500/20 hover:bg-pink-500/40 transition"
            >
              <Linkedin size={18} />
              LinkedIn
            </a>
          </div>
        </motion.div>

        {/* SKILLS */}
        <div className="mt-20">
          <h2 className="text-4xl font-bold mb-8">Tech Stack</h2>

          <div className="flex flex-wrap gap-5">
            {profile.skills.map((skill, index) => (
              <motion.div
                key={index}
                whileHover={{ scale: 1.1, rotate: 3 }}
                className="px-6 py-4 rounded-2xl bg-gradient-to-r from-purple-600 to-cyan-500 text-white font-semibold shadow-xl"
              >
                {skill}
              </motion.div>
            ))}
          </div>
        </div>

        {/* PROJECTS */}
        <div className="mt-20">
          <h2 className="text-4xl font-bold mb-8">Featured Projects</h2>

          <div className="grid md:grid-cols-3 gap-8">
            {profile.projects.map((project, index) => (
              <motion.div
                key={index}
                whileHover={{ scale: 1.04 }}
                className="bg-white/10 border border-white/10 backdrop-blur-xl rounded-[35px] p-8 shadow-2xl"
              >
                <h3 className="text-2xl font-bold mb-4">
                  {project.title}
                </h3>

                <p className="text-gray-300 leading-7 mb-6">
                  {project.description}
                </p>

                <a
                  href={project.link}
                  target="_blank"
                  className="inline-flex items-center gap-2 px-5 py-3 rounded-2xl bg-gradient-to-r from-pink-500 to-purple-500 hover:opacity-80 transition"
                >
                  View Project
                  <ExternalLink size={18} />
                </a>
              </motion.div>
            ))}
          </div>
        </div>

        {/* FOOTER */}
        <motion.div
          initial={{ opacity: 0 }}
          whileInView={{ opacity: 1 }}
          transition={{ duration: 1 }}
          className="mt-24 text-center text-gray-400"
        >
          <h2 className="text-3xl font-bold bg-gradient-to-r from-purple-400 to-cyan-400 bg-clip-text text-transparent">
            Keep Building • Keep Learning • Keep Innovating
          </h2>

          <p className="mt-4">
            Designed with React, Tailwind CSS, Framer Motion & Creativity.
          </p>
        </motion.div>
      </div>
    </div>
  );
}


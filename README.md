export default function GitHubDashboard() {
  const profile = {
    name: "Your Name",
    role: "Full Stack Developer",
    location: "Karnataka, India",
    email: "yourmail@example.com",
    github: "https://github.com/yourusername",
    linkedin: "https://linkedin.com/in/yourprofile",
    bio: "Passionate developer who loves building creative web applications and solving real-world problems.",
    skills: ["Java", "Python", "React", "C", "HTML", "CSS", "JavaScript"],
    projects: [
      {
        title: "Portfolio Website",
        description: "Personal animated portfolio website with responsive design."
      },
      {
        title: "Student Management System",
        description: "Java project for managing student records and attendance."
      },
      {
        title: "Flower Shop Website",
        description: "Creative flower shop webpage using HTML, CSS, and JavaScript."
      }
    ],
    stats: {
      repos: 25,
      followers: 120,
      following: 80,
      contributions: 540
    }
  };

  return (
    <div className="min-h-screen bg-black text-white overflow-hidden relative">
      {/* Animated Background */}
      <div className="absolute inset-0 overflow-hidden">
        <div className="absolute w-72 h-72 bg-purple-500 opacity-20 rounded-full blur-3xl top-10 left-10 animate-pulse"></div>
        <div className="absolute w-72 h-72 bg-blue-500 opacity-20 rounded-full blur-3xl bottom-10 right-10 animate-bounce"></div>
        <div className="absolute w-56 h-56 bg-pink-500 opacity-20 rounded-full blur-3xl top-1/2 left-1/2 animate-ping"></div>
      </div>

      <div className="relative z-10 p-6 md:p-10">
        {/* Header */}
        <div className="flex flex-col md:flex-row items-center justify-between gap-6 mb-10">
          <div className="flex items-center gap-5">
            <div className="w-28 h-28 rounded-full bg-gradient-to-r from-purple-500 to-blue-500 p-1 animate-spin-slow">
              <img
                src="https://avatars.githubusercontent.com/u/9919?s=200&v=4"
                alt="profile"
                className="w-full h-full rounded-full object-cover"
              />
            </div>

            <div>
              <h1 className="text-4xl font-bold tracking-wide">{profile.name}</h1>
              <p className="text-lg text-gray-300 mt-2">{profile.role}</p>
              <p className="text-sm text-gray-400">📍 {profile.location}</p>
            </div>
          </div>

          <div className="flex gap-4">
            <a
              href={profile.github}
              target="_blank"
              className="px-5 py-3 rounded-2xl bg-white text-black font-semibold hover:scale-105 transition-all duration-300"
            >
              GitHub
            </a>

            <a
              href={profile.linkedin}
              target="_blank"
              className="px-5 py-3 rounded-2xl border border-white hover:bg-white hover:text-black transition-all duration-300"
            >
              LinkedIn
            </a>
          </div>
        </div>

        {/* About Section */}
        <div className="grid md:grid-cols-2 gap-8 mb-10">
          <div className="bg-white/10 backdrop-blur-lg rounded-3xl p-6 shadow-2xl hover:scale-105 transition-all duration-500">
            <h2 className="text-2xl font-bold mb-4">About Me</h2>
            <p className="text-gray-300 leading-7">{profile.bio}</p>

            <div className="mt-6 space-y-2 text-gray-300">
              <p>📧 {profile.email}</p>
              <p>💻 Open Source Enthusiast</p>
              <p>🚀 Loves Creative UI Designs</p>
            </div>
          </div>

          {/* GitHub Stats */}
          <div className="grid grid-cols-2 gap-4">
            <div className="bg-purple-500/20 rounded-3xl p-6 text-center hover:-translate-y-2 transition-all duration-500">
              <h3 className="text-3xl font-bold">{profile.stats.repos}</h3>
              <p className="text-gray-300 mt-2">Repositories</p>
            </div>

            <div className="bg-blue-500/20 rounded-3xl p-6 text-center hover:-translate-y-2 transition-all duration-500">
              <h3 className="text-3xl font-bold">{profile.stats.followers}</h3>
              <p className="text-gray-300 mt-2">Followers</p>
            </div>

            <div className="bg-pink-500/20 rounded-3xl p-6 text-center hover:-translate-y-2 transition-all duration-500">
              <h3 className="text-3xl font-bold">{profile.stats.following}</h3>
              <p className="text-gray-300 mt-2">Following</p>
            </div>

            <div className="bg-green-500/20 rounded-3xl p-6 text-center hover:-translate-y-2 transition-all duration-500">
              <h3 className="text-3xl font-bold">{profile.stats.contributions}</h3>
              <p className="text-gray-300 mt-2">Contributions</p>
            </div>
          </div>
        </div>

        {/* Skills */}
        <div className="bg-white/10 backdrop-blur-lg rounded-3xl p-6 mb-10 shadow-2xl">
          <h2 className="text-2xl font-bold mb-6">Skills</h2>

          <div className="flex flex-wrap gap-4">
            {profile.skills.map((skill, index) => (
              <div
                key={index}
                className="px-5 py-3 rounded-2xl bg-gradient-to-r from-purple-500 to-blue-500 hover:scale-110 transition-all duration-300 cursor-pointer"
              >
                {skill}
              </div>
            ))}
          </div>
        </div>

        {/* Projects */}
        <div>
          <h2 className="text-3xl font-bold mb-6">Projects</h2>

          <div className="grid md:grid-cols-3 gap-6">
            {profile.projects.map((project, index) => (
              <div
                key={index}
                className="bg-white/10 backdrop-blur-lg rounded-3xl p-6 shadow-2xl hover:rotate-1 hover:scale-105 transition-all duration-500"
              >
                <h3 className="text-2xl font-semibold mb-3">{project.title}</h3>
                <p className="text-gray-300 leading-6">{project.description}</p>

                <button className="mt-5 px-4 py-2 rounded-xl bg-gradient-to-r from-pink-500 to-purple-500 hover:opacity-80 transition-all duration-300">
                  View Project
                </button>
              </div>
            ))}
          </div>
        </div>

        {/* Footer */}
        <div className="mt-16 text-center text-gray-400">
          <p>✨ Designed with creativity and animations ✨</p>
        </div>
      </div>

      <style>{`
        .animate-spin-slow {
          animation: spin 8s linear infinite;
        }

        @keyframes spin {
          from {
            transform: rotate(0deg);
          }
          to {
            transform: rotate(360deg);
          }
        }
      `}</style>
    </div>
  );
}

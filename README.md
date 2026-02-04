import React, { useEffect, useState } from "react";
import {
  Code2,
  Server,
  Database,
  Cloud,
  Cpu,
  ShieldCheck,
  Terminal,
  Github,
  Linkedin,
  Mail,
  ChevronDown,
  Layers,
  Network,
  Smartphone,
  Braces,
  Boxes,
  GitBranch,
  HardDrive,
} from "lucide-react";

const SKILLS = [
  {
    title: "Frontend",
    icon: Code2,
    items: [
      { name: "React", icon: Braces },
      { name: "Vue.js", icon: Braces },
      { name: "Flutter", icon: Smartphone },
      { name: "TypeScript", icon: Braces },
      { name: "Tailwind CSS", icon: Layers },
    ],
  },
  {
    title: "Backend",
    icon: Server,
    items: [
      { name: ".NET", icon: Boxes },
      { name: "Node.js", icon: Boxes },
      { name: "Express", icon: Boxes },
      { name: "REST APIs", icon: Network },
    ],
  },
  {
    title: "Databases",
    icon: Database,
    items: [
      { name: "SQL Server", icon: HardDrive },
      { name: "PostgreSQL", icon: HardDrive },
      { name: "MongoDB", icon: HardDrive },
      { name: "MySQL", icon: HardDrive },
    ],
  },
  {
    title: "DevOps & Cloud",
    icon: Cloud,
    items: [
      { name: "Docker", icon: Boxes },
      { name: "Linux Server", icon: Terminal },
      { name: "Nginx", icon: Network },
      { name: "GitHub Actions", icon: GitBranch },
    ],
  },
  {
    title: "Networking",
    icon: Network,
    items: [
      { name: "Windows Server", icon: Server },
      { name: "DNS & Firewall", icon: ShieldCheck },
      { name: "NAT & Port Forwarding", icon: Network },
      { name: "IoT Integrations", icon: Cpu },
    ],
  },
  {
    title: "Architecture",
    icon: Layers,
    items: [
      { name: "Clean Architecture", icon: Layers },
      { name: "SOLID Principles", icon: ShieldCheck },
      { name: "Design Patterns", icon: Boxes },
      { name: "Clean Code", icon: Braces },
    ],
  },
];

export default function App() {
  const [visible, setVisible] = useState(false);

  useEffect(() => setVisible(true), []);

  const scrollTo = (id) =>
    document.getElementById(id)?.scrollIntoView({ behavior: "smooth" });

  return (
    <div className="min-h-screen bg-slate-950 text-slate-200">

      {/* NAV */}
      <nav className="fixed top-0 w-full z-50 bg-slate-950/80 backdrop-blur border-b border-slate-800">
        <div className="max-w-6xl mx-auto h-16 px-6 flex items-center justify-between">
          <span className="text-xl font-bold bg-gradient-to-r from-cyan-400 to-indigo-400 bg-clip-text text-transparent">
            M.DEV
          </span>
          <div className="hidden md:flex gap-8 text-sm text-slate-400">
            {["about", "skills", "contact"].map((s) => (
              <button key={s} onClick={() => scrollTo(s)} className="hover:text-cyan-400">
                {s.toUpperCase()}
              </button>
            ))}
          </div>
        </div>
      </nav>

      {/* HERO */}
      <section
        id="about"
        className="pt-32 min-h-screen flex flex-col justify-center px-6 max-w-6xl mx-auto"
      >
        <div className={`transition-all duration-1000 ${visible ? "opacity-100" : "opacity-0 translate-y-6"}`}>
          <span className="inline-flex items-center gap-2 px-3 py-1 mb-6 rounded-full bg-cyan-950/40 border border-cyan-800 text-cyan-400 text-sm">
            <Terminal size={14} /> Full-Stack Developer
          </span>

          <h1 className="text-5xl md:text-7xl font-bold text-white mb-6">
            Mohammed<br />
            <span className="text-transparent bg-clip-text bg-gradient-to-r from-cyan-400 to-indigo-500">
              Clean Architecture Engineer
            </span>
          </h1>

          <p className="max-w-2xl text-xl text-slate-400 mb-10">
            Building scalable systems, production-ready APIs, secure servers,
            and clean maintainable architectures.
          </p>

          <div className="flex gap-4">
            <button
              onClick={() => scrollTo("contact")}
              className="px-8 py-3 bg-cyan-600 hover:bg-cyan-500 rounded-lg flex items-center gap-2"
            >
              <Mail size={18} /> Contact
            </button>
            <a
              href="https://github.com/USERNAME"
              target="_blank"
              rel="noreferrer"
              className="px-8 py-3 bg-slate-800 border border-slate-700 rounded-lg flex items-center gap-2"
            >
              <Github size={18} /> GitHub
            </a>
          </div>
        </div>

        <ChevronDown className="mx-auto mt-20 animate-bounce text-slate-600" />
      </section>

      {/* SKILLS */}
      <section id="skills" className="py-24 px-6 max-w-6xl mx-auto">
        <h2 className="text-center text-4xl font-bold mb-16">Technical Stack</h2>

        <div className="grid md:grid-cols-2 lg:grid-cols-3 gap-6">
          {SKILLS.map(({ title, icon: Icon, items }) => (
            <div
              key={title}
              className="bg-slate-900 border border-slate-800 rounded-2xl p-6 hover:border-slate-700 transition"
            >
              <div className="flex items-center gap-3 mb-6">
                <div className="p-3 bg-cyan-500/10 text-cyan-400 rounded-lg">
                  <Icon size={22} />
                </div>
                <h3 className="text-xl font-bold">{title}</h3>
              </div>

              <div className="flex flex-wrap gap-2">
                {items.map(({ name, icon: I }) => (
                  <span
                    key={name}
                    className="flex items-center gap-2 px-3 py-1 bg-slate-800 border border-slate-700 rounded-md text-sm"
                  >
                    <I size={14} /> {name}
                  </span>
                ))}
              </div>
            </div>
          ))}
        </div>
      </section>

      {/* CONTACT */}
      <section id="contact" className="py-24 text-center bg-slate-900">
        <h2 className="text-3xl font-bold mb-8">Let’s Work Together</h2>
        <div className="flex flex-col md:flex-row gap-6 justify-center">
          <a
            href="https://linkedin.com/in/USERNAME"
            className="px-8 py-4 bg-[#0077b5] rounded-xl flex items-center justify-center gap-3"
          >
            <Linkedin /> LinkedIn
          </a>
          <a
            href="mailto:your@email.com"
            className="px-8 py-4 bg-slate-800 border border-slate-700 rounded-xl flex items-center justify-center gap-3"
          >
            <Mail /> Email
          </a>
        </div>
      </section>
    </div>
  );
}

import React, { useState } from 'react';
import {
  Globe,
  ShieldCheck,
  TrendingUp,
  MessageSquare,
  Users,
  ChevronRight,
  Award,
  Linkedin,
  Mail,
  Phone,
  LayoutGrid,
  Activity,
  Coffee,
  CheckCircle2,
  ExternalLink
} from 'lucide-react';

const App = () => {
  const [isMenuOpen, setIsMenuOpen] = useState(false);

  const scrollToSection = (id) => {
    const element = document.getElementById(id);
    if (element) {
      element.scrollIntoView({ behavior: 'smooth' });
    }
    setIsMenuOpen(false);
  };

  return (
    <div className="min-h-screen bg-slate-50 font-sans text-slate-900">
      <a href="#main-content" className="sr-only focus:not-sr-only focus:fixed focus:top-4 focus:left-4 focus:z-[100] focus:bg-amber-500 focus:text-slate-900 focus:px-4 focus:py-2 focus:rounded-md focus:font-bold">
        Skip to main content
      </a>

      {/* Navigation Header */}
      <header className="fixed top-0 w-full bg-white/95 backdrop-blur-md border-b border-slate-200 z-50">
        <nav className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8" aria-label="Main Navigation">
          <div className="flex justify-between h-20 items-center">
            <button
              onClick={() => scrollToSection('home')}
              className="flex items-center gap-2 group focus-visible:ring-2 focus-visible:ring-amber-500 focus-visible:outline-none rounded-lg p-1"
              aria-label="Akhil Global Exports - Go to top"
            >
              <div className="bg-slate-900 text-white p-2 rounded-lg" aria-hidden="true">
                <Globe size={24} className="text-amber-400" />
              </div>
              <div className="text-left">
                <span className="text-xl font-bold tracking-tight text-slate-900 block leading-none">AKHIL</span>
                <span className="text-[10px] block font-medium text-amber-600 uppercase tracking-widest">Global Exports</span>
              </div>
            </button>

            {/* Desktop Menu */}
            <ul className="hidden md:flex space-x-8 items-center" role="list">
              <li><button onClick={() => scrollToSection('model')} className="text-sm font-semibold hover:text-amber-600 transition-colors focus-visible:ring-2 focus-visible:ring-amber-500 focus-visible:outline-none rounded">Business Model</button></li>
              <li><button onClick={() => scrollToSection('products')} className="text-sm font-semibold hover:text-amber-600 transition-colors focus-visible:ring-2 focus-visible:ring-amber-500 focus-visible:outline-none rounded">Verticals</button></li>
              <li><button onClick={() => scrollToSection('process')} className="text-sm font-semibold hover:text-amber-600 transition-colors focus-visible:ring-2 focus-visible:ring-amber-500 focus-visible:outline-none rounded">Buyer Journey</button></li>
              <li><button onClick={() => scrollToSection('about')} className="text-sm font-semibold hover:text-amber-600 transition-colors focus-visible:ring-2 focus-visible:ring-amber-500 focus-visible:outline-none rounded">Our Founder</button></li>
              <li>
                <button
                  onClick={() => window.open('https://wa.me/918332896316', '_blank')}
                  className="bg-slate-900 text-white px-5 py-2.5 rounded-full text-sm font-bold flex items-center gap-2 hover:bg-slate-800 transition-all shadow-lg focus-visible:ring-2 focus-visible:ring-amber-500 focus-visible:outline-none"
                  aria-label="Contact Akhil Global Exports team via WhatsApp"
                >
                  <MessageSquare size={16} aria-hidden="true" /> Contact Team
                </button>
              </li>
            </ul>

            {/* Mobile Menu Toggle */}
            <button
              className="md:hidden p-2 text-slate-900 focus-visible:ring-2 focus-visible:ring-amber-500"
              onClick={() => setIsMenuOpen(!isMenuOpen)}
              aria-expanded={isMenuOpen}
              aria-label="Toggle navigation menu"
            >
              <LayoutGrid size={24} aria-hidden="true" />
            </button>
          </div>

          {/* Mobile Menu Drawer */}
          {isMenuOpen && (
            <div className="md:hidden pb-6 bg-white border-t border-slate-100 animate-in fade-in slide-in-from-top-4">
              <ul className="flex flex-col space-y-4 pt-4" role="list">
                <li><button onClick={() => scrollToSection('model')} className="block w-full text-left font-semibold py-2">Business Model</button></li>
                <li><button onClick={() => scrollToSection('products')} className="block w-full text-left font-semibold py-2">Verticals</button></li>
                <li><button onClick={() => scrollToSection('process')} className="block w-full text-left font-semibold py-2">Buyer Journey</button></li>
                <li><button onClick={() => scrollToSection('about')} className="block w-full text-left font-semibold py-2">Our Founder</button></li>
              </ul>
            </div>
          )}
        </nav>
      </header>

      <main id="main-content">
        {/* Hero Section */}
        <section id="home" className="pt-32 pb-20 bg-gradient-to-br from-slate-900 to-slate-800 text-white relative" aria-labelledby="hero-heading">
          <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
            <div className="grid lg:grid-cols-2 gap-12 items-center">
              <div>
                <div className="inline-flex items-center gap-2 bg-amber-500/20 border border-amber-500/30 text-amber-400 px-4 py-1.5 rounded-full text-xs font-bold uppercase tracking-widest mb-6">
                  <ShieldCheck size={14} aria-hidden="true" /> India's Trusted Bulk Export Partner
                </div>
                <h1 id="hero-heading" className="text-4xl md:text-6xl font-extrabold leading-tight mb-6">
                  Your Smartest Decision for <span className="text-amber-400">Indian Supply.</span>
                </h1>
                <p className="text-lg text-slate-300 mb-8 max-w-xl">
                  We build responsible, structured trade partnerships for retailers and wholesalers in the USA, Canada, Africa, Europe, and Asia. From documentation to delivery, we handle the tension—you enjoy the growth.
                </p>
                <div className="flex flex-col sm:flex-row gap-4">
                  <button
                    onClick={() => scrollToSection('process')}
                    className="bg-amber-500 text-slate-900 px-8 py-4 rounded-xl font-bold text-lg hover:bg-amber-400 transition-all flex items-center justify-center gap-2 group focus-visible:ring-4 focus-visible:ring-amber-500/50"
                  >
                    Start Your Order <ChevronRight className="group-hover:translate-x-1 transition-transform" aria-hidden="true" />
                  </button>
                  <button
                    onClick={() => window.open('https://wa.me/918332896316', '_blank')}
                    className="bg-white/10 backdrop-blur-md border border-white/20 text-white px-8 py-4 rounded-xl font-bold text-lg hover:bg-white/20 transition-all text-center focus-visible:ring-4 focus-visible:ring-white/30"
                    aria-label="Open WhatsApp for a free business strategy consultation"
                  >
                    WhatsApp Consultation
                  </button>
                </div>
              </div>

              <div className="hidden lg:block">
                <div className="bg-slate-800 aspect-[4/5] rounded-3xl overflow-hidden border-4 border-white/10 shadow-2xl flex flex-col items-center justify-center p-8 text-center relative group">
                  <div className="w-48 h-48 bg-slate-700 rounded-full mb-6 border-4 border-amber-500/30 flex items-center justify-center overflow-hidden">
                    <Users size={64} className="text-amber-500 opacity-50" aria-hidden="true" />
                  </div>
                  <h2 className="text-2xl font-bold">Akhil Kumar Ponnam</h2>
                  <p className="text-amber-400 font-medium italic">CEO, Akhil Global Exports</p>
                  <p className="text-sm text-slate-400 mt-4 max-w-xs">
                    "I build sustainable trade systems that help you scale in your local market."
                  </p>
                  <div className="absolute -bottom-6 -left-6 bg-white text-slate-900 p-4 rounded-xl shadow-2xl z-20 flex items-center gap-3 border-b-4 border-amber-500">
                    <Award className="text-amber-500" aria-hidden="true" />
                    <div>
                      <p className="font-bold text-sm">MBA Strategist</p>
                      <p className="text-[10px] text-slate-500">Personal Brand Driven</p>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </section>

        {/* Value Prop Section */}
        <section id="model" className="py-24 bg-white" aria-labelledby="strategic-heading">
          <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div className="text-center mb-16">
              <p className="text-sm font-bold text-amber-600 uppercase tracking-[0.3em] mb-4">Strategic Advantage</p>
              <h2 id="strategic-heading" className="text-3xl md:text-5xl font-extrabold text-slate-900">Why Global Importers Choose Us</h2>
            </div>
            <div className="grid md:grid-cols-3 gap-8">
              {[
                { icon: <ShieldCheck className="text-blue-600" size={32} />, title: "Zero Documentation Tension", desc: "Phytosanitary, COO, ISO, FSSAI compliance managed end-to-end." },
                { icon: <TrendingUp className="text-green-600" size={32} />, title: "2-6-10 Growth Model", desc: "Designed for scalability. Start with 2-FCL trial, scale to 10 for max margin." },
                { icon: <Award className="text-amber-600" size={32} />, title: "Quality Benchmarking", desc: "Lab-certified batches, triple-inspected for global compliance." }
              ].map((item, i) => (
                <div key={i} className="p-8 rounded-2xl bg-slate-50 border border-slate-100 hover:border-amber-500 transition-all group">
                  <div className="bg-white w-16 h-16 rounded-xl flex items-center justify-center mb-6 shadow-sm" aria-hidden="true">
                    {item.icon}
                  </div>
                  <h3 className="text-xl font-bold mb-4">{item.title}</h3>
                  <p className="text-slate-600 leading-relaxed">{item.desc}</p>
                </div>
              ))}
            </div>
          </div>
        </section>

        {/* Business Ladder Section */}
        <section className="py-24 bg-slate-900 text-white" aria-labelledby="ladder-heading">
          <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div className="grid lg:grid-cols-2 gap-16 items-center">
              <div>
                <p className="text-amber-500 font-bold text-sm uppercase tracking-widest mb-4">The Scale Blueprint</p>
                <h2 id="ladder-heading" className="text-3xl md:text-4xl font-bold mb-6">The 2-6-10 Container Deal Ladder</h2>
                <p className="text-slate-400 mb-8 leading-relaxed">
                  The more you trade with us, the better the unit economics for your retail or wholesale operation.
                </p>
               
                <div className="space-y-6">
                  {[
                    { level: "2 FCL", name: "Starter Importer Deal", benefit: "Buddy Container Rule: Split products or grades. Low commitment trial." },
                    { level: "6 FCL", name: "Growth Deal", benefit: "Better freight efficiency & mixed product inventory management." },
                    { level: "10 FCL", name: "Scale Deal", benefit: "Priority production allocation & best possible unit pricing advantage." }
                  ].map((deal, idx) => (
                    <article key={idx} className="flex gap-4 items-start p-4 bg-white/5 rounded-xl border border-white/10">
                      <div className="bg-amber-500 text-slate-900 font-black px-3 py-1 rounded text-sm shrink-0" aria-hidden="true">
                        {deal.level}
                      </div>
                      <div>
                        <h3 className="font-bold text-lg text-white">{deal.name}</h3>
                        <p className="text-sm text-slate-400">{deal.benefit}</p>
                      </div>
                    </article>
                  ))}
                </div>
              </div>
              <div className="relative p-8 bg-white/5 rounded-3xl border border-white/10" aria-hidden="true">
                <div className="space-y-4">
                  <div className="bg-blue-600 h-16 rounded flex items-center justify-center font-bold">2 FCL</div>
                  <div className="bg-blue-700 h-16 rounded flex items-center justify-center font-bold opacity-75">6 FCL</div>
                  <div className="bg-blue-800 h-16 rounded flex items-center justify-center font-bold opacity-50">10 FCL</div>
                </div>
                <div className="mt-8 text-center text-amber-400 font-black text-2xl">50T+ CAPACITY</div>
              </div>
            </div>
          </div>
        </section>

        {/* Verticals Section */}
        <section id="products" className="py-24 bg-white" aria-labelledby="verticals-heading">
          <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 mb-16">
            <p className="text-sm font-bold text-amber-600 uppercase tracking-[0.3em] mb-4">Export Verticals</p>
            <h2 id="verticals-heading" className="text-3xl md:text-5xl font-extrabold text-slate-900">What We Move Globally</h2>
          </div>

          <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 grid md:grid-cols-2 gap-12">
            {/* Healthcare Vertical */}
            <article className="bg-slate-900 rounded-3xl overflow-hidden shadow-2xl text-white">
              <div className="p-8 bg-gradient-to-br from-blue-600 to-blue-800">
                <Activity className="text-white mb-6" size={48} aria-hidden="true" />
                <h3 className="text-3xl font-extrabold mb-2">Healthcare Trade</h3>
                <p className="text-blue-100 font-medium">Rehabilitation & Assistive Devices (HS 9021)</p>
              </div>
              <div className="p-8">
                <ul className="space-y-4 mb-8" role="list">
                  <li className="flex items-center gap-3">
                    <CheckCircle2 className="text-amber-500" size={20} aria-hidden="true" />
                    <span>Prosthetics & Orthopaedic Appliances</span>
                  </li>
                  <li className="flex items-center gap-3">
                    <CheckCircle2 className="text-amber-500" size={20} aria-hidden="true" />
                    <span>Durable Medical Equipment (DME)</span>
                  </li>
                  <li className="flex items-center gap-3">
                    <CheckCircle2 className="text-amber-500" size={20} aria-hidden="true" />
                    <span>Certified Supply Chains for Global Markets</span>
                  </li>
                </ul>
                <button className="w-full py-4 border-2 border-blue-500 text-blue-400 rounded-xl font-bold hover:bg-blue-500 hover:text-white transition-all focus-visible:ring-4 focus-visible:ring-blue-500/50">
                  Request Healthcare Catalog
                </button>
              </div>
            </article>

            {/* Agri Vertical */}
            <article className="bg-slate-50 rounded-3xl overflow-hidden shadow-xl border border-slate-200">
              <div className="p-8 bg-gradient-to-br from-amber-500 to-amber-600 text-white">
                <Coffee className="text-white mb-6" size={48} aria-hidden="true" />
                <h3 className="text-3xl font-extrabold mb-2">Premium Agri-Exports</h3>
                <p className="text-amber-100 font-medium">Bulk Supply Chain Partners</p>
              </div>
              <div className="p-8">
                <ul className="space-y-4 mb-8" role="list">
                  <li className="flex items-center gap-3">
                    <CheckCircle2 className="text-amber-600" size={20} aria-hidden="true" />
                    <span>Soybean Deoiled Cake (DOC) - 44-48% Protein</span>
                  </li>
                  <li className="flex items-center gap-3">
                    <CheckCircle2 className="text-amber-600" size={20} aria-hidden="true" />
                    <span>Premium Coffee Beans (CCRI Standards)</span>
                  </li>
                  <li className="flex items-center gap-3">
                    <CheckCircle2 className="text-amber-600" size={20} aria-hidden="true" />
                    <span>Bulk Livestock Feed & Grain Supply</span>
                  </li>
                </ul>
                <button className="w-full py-4 bg-slate-900 text-white rounded-xl font-bold hover:bg-slate-800 transition-all focus-visible:ring-4 focus-visible:ring-slate-900/30">
                  Request Agri-Quotes
                </button>
              </div>
            </article>
          </div>
        </section>

        {/* Process Section */}
        <section id="process" className="py-24 bg-slate-50" aria-labelledby="process-heading">
          <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-center mb-16">
            <p className="text-sm font-bold text-amber-600 uppercase tracking-[0.3em] mb-4">The Workflow</p>
            <h2 id="process-heading" className="text-3xl md:text-5xl font-extrabold text-slate-900">How We Execute Your Success</h2>
          </div>
         
          <div className="max-w-5xl mx-auto px-4 relative">
            <div className="absolute top-0 bottom-0 left-[21px] md:left-1/2 w-0.5 bg-slate-200" aria-hidden="true"></div>
           
            <ol className="space-y-12" role="list">
              {[
                { step: "01", title: "Needs Discovery", desc: "Consultation on product grade, volume, and growth planning." },
                { step: "02", title: "Compliance Blueprint", desc: "Mapping documentation needed for your specific jurisdiction." },
                { step: "03", title: "Triple Inspection", desc: "Pre-shipment verification of quality and global safety standards." },
                { step: "04", title: "Vessel Coordination", desc: "Direct routing for maximum speed and lowest freight cost." },
                { step: "05", title: "Arrival & Scale", desc: "Reviewing performance and planning the next FCL ladder step." }
              ].map((item, i) => (
                <li key={i} className={`flex items-start relative ${i % 2 === 0 ? 'md:flex-row-reverse' : ''}`}>
                  <div className="w-11 h-11 bg-amber-500 rounded-full flex items-center justify-center text-slate-900 font-black z-10 shrink-0 border-4 border-white" aria-hidden="true">
                    {item.step}
                  </div>
                  <div className={`ml-8 md:ml-0 md:w-1/2 ${i % 2 === 0 ? 'md:pr-16 text-left md:text-right' : 'md:pl-16 text-left'}`}>
                    <h3 className="text-xl font-bold mb-2 text-slate-900">{item.title}</h3>
                    <p className="text-slate-600">{item.desc}</p>
                  </div>
                </li>
              ))}
            </ol>
          </div>
        </section>

        {/* About Founder */}
        <section id="about" className="py-24 bg-white" aria-labelledby="about-heading">
          <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div className="flex flex-col lg:flex-row gap-16 items-center">
              <div className="lg:w-1/3">
                 <div className="w-full aspect-square bg-slate-900 rounded-3xl overflow-hidden flex items-center justify-center relative group">
                    <LayoutGrid className="text-slate-800" size={120} aria-hidden="true" />
                    <div className="absolute bottom-8 left-8 right-8 text-white">
                      <p className="text-amber-400 font-bold uppercase text-[10px] tracking-widest mb-2">Personal Brand</p>
                      <h3 className="text-2xl font-bold">Akhil Kumar Ponnam</h3>
                      <p className="text-sm text-slate-300">CEO & Tech Strategist</p>
                    </div>
                 </div>
              </div>
             
              <div className="lg:w-2/3">
                <p className="text-sm font-bold text-amber-600 uppercase tracking-widest mb-4">Behind the Brand</p>
                <h2 id="about-heading" className="text-3xl md:text-4xl font-extrabold text-slate-900 mb-6">Built on Strategy, Tech, and Accessibility.</h2>
                <div className="space-y-4 text-slate-600 text-lg">
                  <p>
                    I view trade through the lens of efficiency and inclusion. With a background in Computer Science and an MBA, I treat supply chain as a technology stack—reliable, transparent, and scalable.
                  </p>
                  <p>
                    As an <strong>Accessibility Evangelist</strong>, my goal is to make cross-border trade usable and accessible for every buyer, removing the "documentation tension" that holds back global growth.
                  </p>
                </div>
               
                <div className="mt-8 flex flex-wrap gap-6">
                  <a href="https://linkedin.com" target="_blank" rel="noopener noreferrer" className="flex items-center gap-2 text-slate-600 hover:text-blue-600 transition-colors font-semibold focus-visible:ring-2 focus-visible:ring-blue-600 rounded p-1" aria-label="Visit Akhil's LinkedIn profile (opens in new tab)">
                    <Linkedin size={20} aria-hidden="true" /> LinkedIn
                  </a>
                  <a href="mailto:akhilponnam9@gmail.com" className="flex items-center gap-2 text-slate-600 hover:text-red-500 transition-colors font-semibold focus-visible:ring-2 focus-visible:ring-red-500 rounded p-1" aria-label="Send an email to Akhil">
                    <Mail size={20} aria-hidden="true" /> Email
                  </a>
                  <a href="https://wa.me/918332896316" target="_blank" rel="noopener noreferrer" className="flex items-center gap-2 text-slate-600 hover:text-green-600 transition-colors font-semibold focus-visible:ring-2 focus-visible:ring-green-600 rounded p-1" aria-label="Chat with Akhil on WhatsApp (opens in new tab)">
                    <Phone size={20} aria-hidden="true" /> WhatsApp
                  </a>
                </div>
              </div>
            </div>
          </div>
        </section>
      </main>

      <footer className="bg-slate-900 text-white py-20" role="contentinfo">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div className="bg-gradient-to-r from-amber-500 to-amber-600 rounded-3xl p-10 md:p-16 text-slate-900 text-center mb-20">
             <h2 className="text-3xl md:text-5xl font-black mb-6">Ready to Scale Your Supply?</h2>
             <p className="text-xl mb-10 text-slate-800 font-medium max-w-2xl mx-auto">
               Book a strategy session today. Let's discuss your market and build your custom FCL ladder.
             </p>
             <button
               onClick={() => window.open('https://wa.me/918332896316', '_blank')}
               className="bg-slate-900 text-white px-10 py-5 rounded-2xl font-bold text-xl hover:scale-105 transition-all shadow-2xl flex items-center gap-3 mx-auto focus-visible:ring-4 focus-visible:ring-slate-900/50"
               aria-label="Book a free export strategy session on WhatsApp"
             >
               Book Strategy Session <ExternalLink size={24} aria-hidden="true" />
             </button>
          </div>
         
          <div className="grid md:grid-cols-4 gap-12 border-t border-white/10 pt-16">
            <div className="col-span-1 md:col-span-2">
              <div className="flex items-center gap-2 mb-6" aria-hidden="true">
                <Globe size={32} className="text-amber-400" />
                <span className="text-2xl font-bold tracking-tight">AKHIL GLOBAL EXPORTS</span>
              </div>
              <p className="text-slate-400 max-w-sm">
                India's premier accessibility-driven export house. Specializing in healthcare rehabilitation and premium agri-commodities.
              </p>
            </div>
           
            <div>
              <h3 className="font-bold mb-6 text-amber-500">Global Markets</h3>
              <ul className="space-y-3 text-sm text-slate-400 font-medium" role="list">
                <li>USA & Canada</li>
                <li>Germany & EU</li>
                <li>Ghana & West Africa</li>
                <li>Australia & Asia</li>
              </ul>
            </div>
           
            <div>
              <h3 className="font-bold mb-6 text-amber-500">Contact Team</h3>
              <ul className="space-y-4" role="list">
                <li className="text-sm">
                  <a href="mailto:akhilglobalexports@gmail.com" className="hover:text-amber-400 transition-colors flex items-center gap-2">
                    <Mail size={16} aria-hidden="true" /> akhilglobalexports@gmail.com
                  </a>
                </li>
                <li className="text-sm">
                  <a href="tel:+918332896316" className="hover:text-amber-400 transition-colors flex items-center gap-2">
                    <Phone size={16} aria-hidden="true" /> +91 83328 96316
                  </a>
                </li>
              </ul>
            </div>
          </div>
         
          <div className="mt-20 pt-8 border-t border-white/5 flex flex-col md:flex-row justify-between items-center gap-4 text-[10px] text-slate-600 tracking-widest font-bold">
            <p>© 2026 AKHIL GLOBAL EXPORTS. ACCESSIBILITY DRIVEN TRADE.</p>
            <div className="flex gap-8">
              <a href="#" className="hover:text-white transition-colors">Privacy</a>
              <a href="#" className="hover:text-white transition-colors">Compliance</a>
            </div>
          </div>
        </div>
      </footer>

      {/* Persistent WhatsApp Button */}
      <div className="fixed bottom-6 right-6 z-50">
        <button
          onClick={() => window.open('https://wa.me/918332896316', '_blank')}
          className="bg-green-600 text-white p-4 rounded-full shadow-2xl hover:scale-110 active:scale-95 transition-all focus-visible:ring-4 focus-visible:ring-green-600/50"
          aria-label="Chat with the Akhil Global Exports team on WhatsApp"
        >
          <MessageSquare size={24} aria-hidden="true" />
        </button>
      </div>
    </div>
  );
};

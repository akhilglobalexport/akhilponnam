import React, { useState, useEffect } from 'react';
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
  ExternalLink,
  Menu,
  X,
  FileCheck
} from 'lucide-react';

/**
 * Akhil Global Exports - Official Business Website
 * Focus: International Trade Strategy, Accessibility, and Bulk Supply
 * Standards: WCAG 2.2 Compliant, Responsive, Personal Brand Driven
 */

const App = () => {
  const [isMenuOpen, setIsMenuOpen] = useState(false);
  const [scrolled, setScrolled] = useState(false);

  // Handle scroll effect for header shadow
  useEffect(() => {
    const handleScroll = () => {
      setScrolled(window.scrollY > 20);
    };
    window.addEventListener('scroll', handleScroll);
    return () => window.removeEventListener('scroll', handleScroll);
  }, []);

  const scrollToSection = (id) => {
    const element = document.getElementById(id);
    if (element) {
      element.scrollIntoView({ behavior: 'smooth' });
    }
    setIsMenuOpen(false);
  };

  return (
    <div className="min-h-screen bg-slate-50 font-sans text-slate-900 selection:bg-amber-200 selection:text-slate-900">
      {/* 1. Skip to Content Link (Accessibility Requirement) */}
      <a
        href="#main-content"
        className="sr-only focus:not-sr-only focus:fixed focus:top-4 focus:left-4 focus:z-[100] focus:bg-amber-500 focus:text-slate-900 focus:px-6 focus:py-3 focus:rounded-lg focus:font-bold focus:shadow-2xl focus:outline-none focus:ring-4 focus:ring-amber-300"
      >
        Skip to main content
      </a>

      {/* 2. Navigation Header (Semantic Landmark) */}
      <header
        className={`fixed top-0 w-full z-50 transition-all duration-300 ${
          scrolled ? 'bg-white/95 backdrop-blur-md shadow-md border-b border-slate-200' : 'bg-transparent py-2'
        }`}
      >
        <nav className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8" aria-label="Main Navigation">
          <div className="flex justify-between h-20 items-center">
            {/* Logo Button */}
            <button
              onClick={() => scrollToSection('home')}
              className="flex items-center gap-3 group focus-visible:ring-4 focus-visible:ring-amber-400 focus-visible:outline-none rounded-xl p-1"
              aria-label="Akhil Global Exports Home"
            >
              <div className="bg-slate-900 text-white p-2.5 rounded-xl shadow-lg group-hover:bg-amber-500 transition-colors" aria-hidden="true">
                <Globe size={28} className="text-amber-400 group-hover:text-slate-900" />
              </div>
              <div className="text-left">
                <span className={`text-xl font-black tracking-tight block leading-none ${scrolled ? 'text-slate-900' : 'text-slate-900 md:text-white'}`}>AKHIL</span>
                <span className={`text-[10px] block font-bold uppercase tracking-widest ${scrolled ? 'text-amber-600' : 'text-amber-500 md:text-amber-400'}`}>Global Exports</span>
              </div>
            </button>

            {/* Desktop Navigation */}
            <ul className="hidden md:flex space-x-10 items-center" role="list">
              <li><button onClick={() => scrollToSection('model')} className={`text-sm font-bold transition-colors hover:text-amber-500 focus-visible:ring-2 focus-visible:ring-amber-500 rounded p-1 ${scrolled ? 'text-slate-700' : 'text-slate-900 md:text-slate-100'}`}>Business Model</button></li>
              <li><button onClick={() => scrollToSection('products')} className={`text-sm font-bold transition-colors hover:text-amber-500 focus-visible:ring-2 focus-visible:ring-amber-500 rounded p-1 ${scrolled ? 'text-slate-700' : 'text-slate-900 md:text-slate-100'}`}>Verticals</button></li>
              <li><button onClick={() => scrollToSection('process')} className={`text-sm font-bold transition-colors hover:text-amber-500 focus-visible:ring-2 focus-visible:ring-amber-500 rounded p-1 ${scrolled ? 'text-slate-700' : 'text-slate-900 md:text-slate-100'}`}>Buyer Journey</button></li>
              <li><button onClick={() => scrollToSection('about')} className={`text-sm font-bold transition-colors hover:text-amber-500 focus-visible:ring-2 focus-visible:ring-amber-500 rounded p-1 ${scrolled ? 'text-slate-700' : 'text-slate-900 md:text-slate-100'}`}>Our Founder</button></li>
              <li>
                <button
                  onClick={() => window.open('https://wa.me/918332896316', '_blank')}
                  className="bg-amber-500 text-slate-900 px-6 py-3 rounded-full text-sm font-black flex items-center gap-2 hover:bg-amber-400 hover:scale-105 active:scale-95 transition-all shadow-lg focus-visible:ring-4 focus-visible:ring-amber-400 focus-visible:outline-none"
                  aria-label="Connect with our team via WhatsApp"
                >
                  <MessageSquare size={18} aria-hidden="true" /> Contact Team
                </button>
              </li>
            </ul>

            {/* Mobile Menu Toggle */}
            <button
              className={`md:hidden p-3 rounded-xl transition-colors ${scrolled ? 'text-slate-900 hover:bg-slate-100' : 'text-slate-900 md:text-white hover:bg-white/10'}`}
              onClick={() => setIsMenuOpen(!isMenuOpen)}
              aria-expanded={isMenuOpen}
              aria-controls="mobile-menu"
              aria-label={isMenuOpen ? "Close navigation menu" : "Open navigation menu"}
            >
              {isMenuOpen ? <X size={28} /> : <Menu size={28} />}
            </button>
          </div>

          {/* Mobile Menu Drawer */}
          {isMenuOpen && (
            <div id="mobile-menu" className="md:hidden pb-8 pt-4 bg-white rounded-b-3xl shadow-2xl border-t border-slate-100 animate-in fade-in slide-in-from-top-4">
              <ul className="flex flex-col space-y-2 px-4" role="list">
                <li><button onClick={() => scrollToSection('model')} className="block w-full text-left font-bold py-4 px-4 hover:bg-slate-50 rounded-xl">Business Model</button></li>
                <li><button onClick={() => scrollToSection('products')} className="block w-full text-left font-bold py-4 px-4 hover:bg-slate-50 rounded-xl">Verticals</button></li>
                <li><button onClick={() => scrollToSection('process')} className="block w-full text-left font-bold py-4 px-4 hover:bg-slate-50 rounded-xl">Buyer Journey</button></li>
                <li><button onClick={() => scrollToSection('about')} className="block w-full text-left font-bold py-4 px-4 hover:bg-slate-50 rounded-xl">Our Founder</button></li>
                <li>
                  <button
                    onClick={() => window.open('https://wa.me/918332896316', '_blank')}
                    className="w-full bg-slate-900 text-white font-black py-5 rounded-2xl flex items-center justify-center gap-3 mt-4"
                  >
                    <MessageSquare size={20} /> WhatsApp Team
                  </button>
                </li>
              </ul>
            </div>
          )}
        </nav>
      </header>

      {/* 3. Main Content (Semantic Landmark) */}
      <main id="main-content">
        {/* Hero Section */}
        <section
          id="home"
          className="pt-32 pb-24 md:pt-48 md:pb-36 bg-slate-900 text-white relative overflow-hidden"
          aria-labelledby="hero-heading"
        >
          {/* Subtle decorative background */}
          <div className="absolute inset-0 opacity-5 pointer-events-none" aria-hidden="true">
            <div className="absolute top-0 left-0 w-full h-full bg-[radial-gradient(circle_at_center,_var(--tw-gradient-stops))] from-amber-400 via-transparent to-transparent"></div>
          </div>

          <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
            <div className="grid lg:grid-cols-2 gap-16 items-center">
              <div className="animate-in fade-in slide-in-from-left duration-700">
                <div className="inline-flex items-center gap-2 bg-amber-500/10 border border-amber-500/20 text-amber-400 px-5 py-2 rounded-full text-xs font-black uppercase tracking-[0.2em] mb-8">
                  <ShieldCheck size={16} aria-hidden="true" /> India's Strategic Trade Partner
                </div>
                <h1 id="hero-heading" className="text-4xl md:text-7xl font-black leading-tight mb-8">
                  Your Smartest Path to <span className="text-amber-500">Indian Supply.</span>
                </h1>
                <p className="text-xl text-slate-400 mb-10 max-w-xl leading-relaxed">
                  We build structured, zero-tension trade partnerships connecting certified Indian supply chains with retailers and wholesalers in the USA, Canada, Africa, and Europe.
                </p>
                <div className="flex flex-col sm:flex-row gap-5">
                  <button
                    onClick={() => scrollToSection('process')}
                    className="bg-amber-500 text-slate-900 px-10 py-5 rounded-2xl font-black text-lg hover:bg-amber-400 hover:scale-105 transition-all flex items-center justify-center gap-3 shadow-xl focus-visible:ring-4 focus-visible:ring-amber-400/50"
                  >
                    Start Your Order <ChevronRight className="group-hover:translate-x-1 transition-transform" aria-hidden="true" />
                  </button>
                  <button
                    onClick={() => window.open('https://wa.me/918332896316', '_blank')}
                    className="bg-white/5 border border-white/10 text-white px-10 py-5 rounded-2xl font-black text-lg hover:bg-white/10 transition-all text-center focus-visible:ring-4 focus-visible:ring-white/20"
                    aria-label="Contact Akhil Kumar Ponnam for a business consultation"
                  >
                    Consult CEO
                  </button>
                </div>
              </div>

              <div className="hidden lg:block animate-in fade-in zoom-in duration-1000 delay-200">
                <div className="bg-slate-800/50 backdrop-blur-sm aspect-[4/5] rounded-[3rem] overflow-hidden border border-white/10 shadow-2xl flex flex-col items-center justify-center p-12 text-center relative">
                  <div className="w-56 h-56 bg-slate-700 rounded-full mb-8 border-8 border-amber-500/10 flex items-center justify-center relative shadow-inner">
                    <Users size={80} className="text-amber-500 opacity-40" aria-hidden="true" />
                    <div className="absolute -right-2 -top-2 bg-amber-500 text-slate-900 p-4 rounded-2xl shadow-xl font-black text-sm">MBA</div>
                  </div>
                  <h2 className="text-3xl font-black text-white mb-2">Akhil Kumar Ponnam</h2>
                  <p className="text-amber-400 font-bold uppercase tracking-widest text-xs mb-6">Founder & CEO, Business Strategist</p>
                  <p className="text-lg text-slate-400 italic max-w-sm">
                    "I don't just export products. I design global ecosystems that empower retailers to scale without documentation stress."
                  </p>
                 
                  {/* Trust Badge */}
                  <div className="absolute -bottom-8 right-12 bg-white text-slate-900 p-6 rounded-3xl shadow-2xl border-b-4 border-amber-500 flex items-center gap-4">
                    <div className="bg-slate-100 p-3 rounded-2xl">
                      <Award className="text-amber-600" size={32} aria-hidden="true" />
                    </div>
                    <div className="text-left">
                      <p className="text-xs text-slate-500 font-bold uppercase tracking-widest">Global Focus</p>
                      <p className="font-black text-lg">USA • CA • EU • AF</p>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </section>

        {/* 4. Strategic Advantages (H2 Section) */}
        <section id="model" className="py-24 bg-white" aria-labelledby="advantages-heading">
          <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div className="text-center mb-20">
              <p className="text-sm font-black text-amber-600 uppercase tracking-[0.4em] mb-4">Strategic Framework</p>
              <h2 id="advantages-heading" className="text-4xl md:text-6xl font-black text-slate-900">The Smart Choice Advantage</h2>
            </div>
           
            <div className="grid md:grid-cols-3 gap-10">
              {[
                {
                  icon: <FileCheck className="text-blue-600" size={36} />,
                  title: "Zero Documentation Tension",
                  desc: "We own the complexity. From Phytosanitary and COO to ISO and FSSAI, we handle all compliance so you can focus on selling."
                },
                {
                  icon: <TrendingUp className="text-green-600" size={36} />,
                  title: "2-6-10 Container Model",
                  desc: "Scale your business with logic. Start with a 2-FCL trial, optimize with 6-FCL, and maximize margins with our 10-FCL scale deal."
                },
                {
                  icon: <ShieldCheck className="text-amber-600" size={36} />,
                  title: "Technical Quality Audits",
                  desc: "Every batch is lab-certified. We represent Indian origin with strict adherence to CCRI and international quality benchmarks."
                }
              ].map((item, i) => (
                <article key={i} className="p-10 rounded-[2.5rem] bg-slate-50 border border-slate-100 hover:border-amber-400 hover:bg-white hover:shadow-2xl transition-all duration-300 group">
                  <div className="bg-white w-20 h-20 rounded-2xl flex items-center justify-center mb-8 shadow-sm group-hover:scale-110 transition-transform" aria-hidden="true">
                    {item.icon}
                  </div>
                  <h3 className="text-2xl font-black mb-4 text-slate-900 leading-tight">{item.title}</h3>
                  <p className="text-slate-600 leading-relaxed text-lg">{item.desc}</p>
                </article>
              ))}
            </div>
          </div>
        </section>

        {/* 5. Scale Ladder (H2 Section) */}
        <section className="py-24 bg-slate-900 text-white relative overflow-hidden" aria-labelledby="ladder-heading">
          <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
            <div className="grid lg:grid-cols-2 gap-20 items-center">
              <div>
                <p className="text-amber-500 font-black text-sm uppercase tracking-widest mb-4">The Scalability Blueprint</p>
                <h2 id="ladder-heading" className="text-4xl md:text-5xl font-black mb-8 leading-tight">Grow Your Profits with our <br />2-6-10 Deal Ladder</h2>
                <p className="text-xl text-slate-400 mb-12 leading-relaxed">
                  We don't believe in one-off transactions. We partner with wholesalers to build a sustainable inventory pipeline.
                </p>
               
                <div className="space-y-6" role="list">
                  {[
                    { level: "2 FCL", name: "Starter Importer Deal", benefit: "Buddy Container Rule: Split products/grades. Low commitment test market demand." },
                    { level: "6 FCL", name: "Market Growth Deal", benefit: "Freight efficiency optimization and priority shipping stability." },
                    { level: "10 FCL", name: "Enterprise Scale Deal", benefit: "Best possible unit pricing & priority production allocation from Indian heartlands." }
                  ].map((deal, idx) => (
                    <div key={idx} className="flex gap-6 items-start p-6 bg-white/5 rounded-3xl border border-white/10 hover:bg-white/10 transition-all">
                      <div className="bg-amber-500 text-slate-900 font-black px-4 py-2 rounded-xl text-sm shrink-0 shadow-lg" aria-hidden="true">
                        {deal.level}
                      </div>
                      <div>
                        <h3 className="font-black text-xl text-white mb-2">{deal.name}</h3>
                        <p className="text-slate-400 leading-relaxed">{deal.benefit}</p>
                      </div>
                    </div>
                  ))}
                </div>
              </div>
             
              <div className="relative p-12 bg-white/5 rounded-[3rem] border border-white/10" aria-hidden="true">
                <div className="flex flex-col gap-6">
                  <div className="h-20 bg-blue-600/20 border border-blue-500/30 rounded-2xl flex items-center justify-between px-8">
                    <span className="font-black text-xl text-blue-400 uppercase tracking-widest">Starter</span>
                    <span className="bg-blue-500 text-white font-bold px-3 py-1 rounded-lg">2 FCL</span>
                  </div>
                  <div className="h-20 bg-amber-500/20 border border-amber-500/30 rounded-2xl flex items-center justify-between px-8">
                    <span className="font-black text-xl text-amber-400 uppercase tracking-widest">Growth</span>
                    <span className="bg-amber-500 text-slate-900 font-bold px-3 py-1 rounded-lg">6 FCL</span>
                  </div>
                  <div className="h-20 bg-green-600/20 border border-green-500/30 rounded-2xl flex items-center justify-between px-8">
                    <span className="font-black text-xl text-green-400 uppercase tracking-widest">Scale</span>
                    <span className="bg-green-500 text-white font-bold px-3 py-1 rounded-lg">10 FCL</span>
                  </div>
                </div>
                <div className="mt-12 text-center">
                  <p className="text-amber-500 font-black text-4xl mb-2">50-250 Metric Tonnes</p>
                  <p className="text-slate-500 uppercase tracking-[0.2em] font-bold text-xs">Direct Bulk Export Capacity</p>
                </div>
              </div>
            </div>
          </div>
        </section>

        {/* 6. Product Verticals (H2 Section) */}
        <section id="products" className="py-24 bg-white" aria-labelledby="verticals-heading">
          <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 mb-20">
            <div className="flex flex-col md:flex-row md:items-end justify-between gap-6">
              <div>
                <p className="text-sm font-black text-amber-600 uppercase tracking-[0.3em] mb-4">Core Verticals</p>
                <h2 id="verticals-heading" className="text-4xl md:text-6xl font-black text-slate-900">Supply Solutions</h2>
              </div>
              <p className="text-slate-500 text-lg max-w-sm md:text-right">
                Specialized in high-value rehabilitation and premium bulk agricultural commodities.
              </p>
            </div>
          </div>

          <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 grid md:grid-cols-2 gap-12">
            {/* Healthcare Vertical Card */}
            <article className="bg-slate-900 rounded-[3rem] overflow-hidden shadow-2xl text-white flex flex-col group">
              <div className="p-12 bg-gradient-to-br from-blue-700 to-indigo-900 relative">
                <Activity className="text-white mb-8 group-hover:scale-110 transition-transform" size={64} aria-hidden="true" />
                <h3 className="text-4xl font-black mb-4">Healthcare Trade</h3>
                <p className="text-blue-200 font-bold text-lg">HS Code: 9021 • Rehabilitation focus</p>
                {/* Decorative circle */}
                <div className="absolute -right-8 -top-8 w-32 h-32 bg-white/10 rounded-full"></div>
              </div>
              <div className="p-12 flex-grow">
                <ul className="space-y-5 mb-12" role="list">
                  {[
                    "Prosthetics & Orthopaedic Appliances",
                    "Mobility & Assistive Devices",
                    "Durable Medical Equipment (DME)",
                    "Certified Supply for West African Hubs"
                  ].map((text, idx) => (
                    <li key={idx} className="flex items-center gap-4 text-lg">
                      <CheckCircle2 className="text-amber-500 shrink-0" size={24} aria-hidden="true" />
                      <span>{text}</span>
                    </li>
                  ))}
                </ul>
                <button
                   className="w-full py-5 bg-white text-slate-900 rounded-2xl font-black text-lg hover:bg-blue-500 hover:text-white transition-all shadow-xl focus-visible:ring-4 focus-visible:ring-blue-500/50"
                   aria-label="Request our Healthcare Product Catalog"
                >
                  Request Medical Catalog
                </button>
              </div>
            </article>

            {/* Agri Vertical Card */}
            <article className="bg-slate-50 rounded-[3rem] overflow-hidden shadow-xl border border-slate-200 flex flex-col group">
              <div className="p-12 bg-gradient-to-br from-amber-500 to-amber-600 text-white relative">
                <Coffee className="text-white mb-8 group-hover:scale-110 transition-transform" size={64} aria-hidden="true" />
                <h3 className="text-4xl font-black mb-4">Premium Agri</h3>
                <p className="text-amber-100 font-bold text-lg">High-Grade Bulk Export</p>
                <div className="absolute -right-8 -top-8 w-32 h-32 bg-slate-900/10 rounded-full"></div>
              </div>
              <div className="p-12 flex-grow">
                <ul className="space-y-5 mb-12" role="list">
                  {[
                    "Soybean DOC (44-48% Crude Protein)",
                    "Premium Coffee (Arabica & Robusta)",
                    "Bulk Livestock Feed (Maize/Rice Bran)",
                    "Direct Vessel Routing to EU & Africa"
                  ].map((text, idx) => (
                    <li key={idx} className="flex items-center gap-4 text-lg">
                      <CheckCircle2 className="text-amber-600 shrink-0" size={24} aria-hidden="true" />
                      <span className="text-slate-800 font-medium">{text}</span>
                    </li>
                  ))}
                </ul>
                <button
                  className="w-full py-5 bg-slate-900 text-white rounded-2xl font-black text-lg hover:bg-slate-800 transition-all shadow-xl focus-visible:ring-4 focus-visible:ring-slate-900/30"
                  aria-label="Request bulk pricing for Agri products"
                >
                  Request Agri-Quotes
                </button>
              </div>
            </article>
          </div>
        </section>

        {/* 7. Structured Buyer Journey (H2 Section) */}
        <section id="process" className="py-24 bg-slate-50" aria-labelledby="journey-heading">
          <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-center mb-20">
            <p className="text-sm font-black text-amber-600 uppercase tracking-[0.4em] mb-4">The Workflow</p>
            <h2 id="journey-heading" className="text-4xl md:text-6xl font-black text-slate-900">How We Execute Your Success</h2>
          </div>
         
          <div className="max-w-4xl mx-auto px-4 relative">
            {/* Visual Line */}
            <div className="absolute top-0 bottom-0 left-[21px] md:left-1/2 w-1 bg-slate-200" aria-hidden="true"></div>
           
            <ol className="space-y-16" role="list">
              {[
                { step: "01", title: "Strategic Discovery", desc: "We analyze your market demand, product grades, and growth potential to build your custom FCL deal." },
                { step: "02", title: "Compliance Mapping", desc: "Our team blueprints all documentation requirements—Phyto, COO, FSSAI—specific to your landing port." },
                { step: "03", title: "Triple-Layer Inspection", desc: "Rigorous pre-shipment lab testing and physical quality audits to ensure zero arrival rejection." },
                { step: "04", title: "Vessel Optimization", desc: "Direct vessel coordination to reduce transit time and landed cost for USA, EU, and African routes." },
                { step: "05", title: "Delivery & Re-Scale", desc: "Successful arrival at port. We review your sell-through data and plan your next FCL ladder step." }
              ].map((item, i) => (
                <li key={i} className={`flex items-start relative ${i % 2 === 0 ? 'md:flex-row-reverse' : ''}`}>
                  <div className="w-12 h-12 bg-amber-500 rounded-2xl flex items-center justify-center text-slate-900 font-black text-xl z-10 shrink-0 border-4 border-white shadow-lg" aria-hidden="true">
                    {item.step}
                  </div>
                  <div className={`ml-10 md:ml-0 md:w-1/2 ${i % 2 === 0 ? 'md:pr-20 text-left md:text-right' : 'md:pl-20 text-left'}`}>
                    <h3 className="text-2xl font-black mb-3 text-slate-900 leading-tight">{item.title}</h3>
                    <p className="text-lg text-slate-600 leading-relaxed">{item.desc}</p>
                  </div>
                </li>
              ))}
            </ol>
          </div>
        </section>

        {/* 8. Founder About (H2 Section) */}
        <section id="about" className="py-24 bg-white" aria-labelledby="about-heading">
          <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div className="flex flex-col lg:flex-row gap-20 items-center">
              <div className="lg:w-1/3 w-full">
                 <div className="w-full aspect-square bg-slate-900 rounded-[3rem] overflow-hidden flex items-center justify-center relative shadow-2xl group">
                    <LayoutGrid className="text-slate-800" size={160} aria-hidden="true" />
                    <div className="absolute inset-0 bg-gradient-to-t from-slate-900 via-transparent to-transparent opacity-60"></div>
                    <div className="absolute bottom-10 left-10 right-10 text-white">
                      <p className="text-amber-400 font-black uppercase text-[10px] tracking-[0.3em] mb-3">Principal Partner</p>
                      <h3 className="text-3xl font-black">Akhil Kumar <br />Ponnam</h3>
                      <p className="text-sm text-slate-400 font-bold mt-2">B.E. • MBA • Trade Strategist</p>
                    </div>
                 </div>
              </div>
             
              <div className="lg:w-2/3">
                <p className="text-sm font-black text-amber-600 uppercase tracking-widest mb-4">Leadership</p>
                <h2 id="about-heading" className="text-4xl md:text-5xl font-black text-slate-900 mb-8 leading-tight">Built on Strategy, Tech, <br />and Human Connection.</h2>
                <div className="space-y-6 text-slate-600 text-xl leading-relaxed">
                  <p>
                    I view trade as a <strong>Technology Stack</strong>—it must be reliable, transparent, and scalable. With a background in Computer Science and an MBA in Marketing, I bridge the gap between traditional Indian heartland supply and the fast-paced demands of global retailers.
                  </p>
                  <p>
                    As an <strong>Accessibility Evangelist</strong>, my mission is to make international trade "usable" for my clients. I remove the <strong>"Documentation Tension"</strong> that stops growth, allowing wholesalers to import from India as easily as buying from a local distributor.
                  </p>
                  <p className="font-black text-slate-900 italic">
                    "We don't sell products; we provide the strategic infrastructure for your business to scale globally."
                  </p>
                </div>
               
                <div className="mt-12 flex flex-wrap gap-8">
                  <a href="https://www.linkedin.com/in/akhil-kumar-ponnam-4b680b2a4" target="_blank" rel="noopener noreferrer" className="flex items-center gap-3 text-slate-900 hover:text-blue-600 transition-colors font-black text-lg focus-visible:ring-2 focus-visible:ring-blue-600 rounded-lg p-2" aria-label="Akhil Ponnam LinkedIn profile">
                    <Linkedin size={24} aria-hidden="true" /> LinkedIn
                  </a>
                  <a href="mailto:akhilponnam9@gmail.com" className="flex items-center gap-3 text-slate-900 hover:text-red-600 transition-colors font-black text-lg focus-visible:ring-2 focus-visible:ring-red-600 rounded-lg p-2" aria-label="Send email to Akhil">
                    <Mail size={24} aria-hidden="true" /> Email
                  </a>
                  <a href="https://wa.me/918332896316" target="_blank" rel="noopener noreferrer" className="flex items-center gap-3 text-slate-900 hover:text-green-600 transition-colors font-black text-lg focus-visible:ring-2 focus-visible:ring-green-600 rounded-lg p-2" aria-label="Message Akhil on WhatsApp">
                    <Phone size={24} aria-hidden="true" /> WhatsApp
                  </a>
                </div>
              </div>
            </div>
          </div>
        </section>
      </main>

      {/* 9. Footer with CTA (Semantic Landmark) */}
      <footer className="bg-slate-900 text-white py-24" role="contentinfo">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div className="bg-gradient-to-br from-amber-500 to-amber-600 rounded-[3rem] p-12 md:p-20 text-slate-900 text-center mb-24 relative overflow-hidden shadow-2xl">
             <div className="relative z-10">
               <h2 className="text-4xl md:text-6xl font-black mb-8 leading-tight">Secure Your Supply Ladder.</h2>
               <p className="text-xl md:text-2xl mb-12 text-slate-900 font-bold max-w-2xl mx-auto opacity-90 leading-relaxed">
                 Book a direct strategy consultation with the CEO to build your 2-6-10 scale deal today.
               </p>
               <button
                 onClick={() => window.open('https://wa.me/918332896316', '_blank')}
                 className="bg-slate-900 text-white px-12 py-6 rounded-3xl font-black text-2xl hover:scale-105 active:scale-95 transition-all shadow-2xl flex items-center gap-4 mx-auto focus-visible:ring-4 focus-visible:ring-slate-900/50"
                 aria-label="Book your free export strategy session via WhatsApp"
               >
                 Book Strategy Session <ExternalLink size={28} aria-hidden="true" />
               </button>
             </div>
             {/* Decorative element */}
             <div className="absolute top-0 right-0 w-96 h-96 bg-white/10 rounded-full -translate-y-1/2 translate-x-1/2 blur-3xl" aria-hidden="true"></div>
          </div>
         
          <div className="grid md:grid-cols-4 gap-16 border-t border-white/10 pt-20">
            <div className="col-span-1 md:col-span-2">
              <div className="flex items-center gap-3 mb-8" aria-hidden="true">
                <Globe size={40} className="text-amber-500" />
                <span className="text-3xl font-black tracking-tight">AKHIL GLOBAL EXPORTS</span>
              </div>
              <p className="text-xl text-slate-400 max-w-md leading-relaxed mb-8">
                India's premier personal-brand-driven export house. We transform complex Indian supply chains into accessible global growth systems.
              </p>
            </div>
           
            <div>
              <h3 className="font-black text-lg mb-8 text-amber-500 uppercase tracking-widest">Global Markets</h3>
              <ul className="space-y-4 text-slate-400 font-bold" role="list">
                <li>USA & Canada</li>
                <li>Germany, France & EU</li>
                <li>Ghana & West Africa</li>
                <li>Australia & Asian Hubs</li>
              </ul>
            </div>
           
            <div>
              <h3 className="font-black text-lg mb-8 text-amber-500 uppercase tracking-widest">Connect</h3>
              <address className="not-italic space-y-6">
                <p className="flex items-center gap-4 group">
                  <Mail size={20} className="text-slate-500 group-hover:text-amber-500 transition-colors" aria-hidden="true" />
                  <a href="mailto:akhilglobalexports@gmail.com" className="text-slate-300 hover:text-amber-400 font-bold transition-colors">akhilglobalexports@gmail.com</a>
                </p>
                <p className="flex items-center gap-4 group">
                  <Phone size={20} className="text-slate-500 group-hover:text-amber-500 transition-colors" aria-hidden="true" />
                  <a href="tel:+918332896316" className="text-slate-300 hover:text-amber-400 font-bold transition-colors">+91 83328 96316</a>
                </p>
              </address>
            </div>
          </div>
         
          <div className="mt-24 pt-10 border-t border-white/5 flex flex-col md:flex-row justify-between items-center gap-6 text-xs text-slate-500 tracking-[0.3em] font-black uppercase">
            <p>© 2026 AKHIL GLOBAL EXPORTS. BUILT FOR ACCESSIBLE GLOBAL TRADE.</p>
            <div className="flex gap-12">
              <a href="#" className="hover:text-white transition-colors">Privacy Policy</a>
              <a href="#" className="hover:text-white transition-colors">Compliance</a>
            </div>
          </div>
        </div>
      </footer>

      {/* Persistent Accessibility & Chat Trigger */}
      <div className="fixed bottom-8 right-8 z-50">
        <button
          onClick={() => window.open('https://wa.me/918332896316', '_blank')}
          className="bg-green-600 text-white p-5 rounded-2xl shadow-2xl hover:scale-110 active:scale-95 transition-all group focus-visible:ring-4 focus-visible:ring-green-500/50"
          aria-label="Direct WhatsApp message to our strategy team"
        >
          <MessageSquare size={32} aria-hidden="true" />
          <span className="absolute right-full mr-4 top-1/2 -translate-y-1/2 bg-slate-900 text-white px-4 py-2 rounded-xl text-xs font-black whitespace-nowrap opacity-0 group-hover:opacity-100 transition-opacity pointer-events-none shadow-xl border border-white/10" aria-hidden="true">
            CHAT WITH CEO
          </span>
        </button>
      </div>
    </div>
  );
};

export default App;

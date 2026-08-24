import { useState, useEffect } from 'react';
import { Menu, X, ArrowRight, CheckCircle2, Sparkles, Target, Users, Zap, TrendingUp, Search, Heart, MessageCircle, Calendar, Bell, Shield, Star, ChevronRight, PlayCircle, Plug } from 'lucide-react';

const LandingPage = ({ onGetStarted, onLogin }) => {
  const [menuOpen, setMenuOpen] = useState(false);

  useEffect(() => {
    const style = document.createElement('style');
    style.textContent = `

      * { font-family: 'Inter', sans-serif; }
      @keyframes fadeUp { from { opacity: 0; transform: translateY(30px); } to { opacity: 1; transform: translateY(0); } }
      @keyframes float { 0%, 100% { transform: translateY(0px); } 50% { transform: translateY(-15px); } }
      @keyframes pulse2 { 0%, 100% { opacity: 1; } 50% { opacity: 0.7; } }
      @keyframes growBar { from { height: 0; } }
      .animate-fade-up { animation: fadeUp 0.8s ease-out both; }
      .animate-float { animation: float 6s ease-in-out infinite; }
      .animate-pulse-slow { animation: pulse2 3s ease-in-out infinite; }
      .reveal { opacity: 0; transition: opacity 0.8s ease, transform 0.8s ease; transform: translateY(20px); }
      .reveal.active { opacity: 1; transform: translateY(0); }
      .bar-animate { animation: growBar 1s ease-out both; }
      .stagger > * { opacity: 0; animation: fadeUp 0.6s ease-out forwards; }
      .stagger > *:nth-child(1) { animation-delay: 0.1s; }
      .stagger > *:nth-child(2) { animation-delay: 0.2s; }
      .stagger > *:nth-child(3) { animation-delay: 0.3s; }
      .stagger > *:nth-child(4) { animation-delay: 0.4s; }
      .stagger > *:nth-child(5) { animation-delay: 0.5s; }
      .stagger > *:nth-child(6) { animation-delay: 0.6s; }
    `;
    document.head.appendChild(style);

    const observer = new IntersectionObserver((entries) => {
      entries.forEach(entry => { if (entry.isIntersecting) entry.target.classList.add('active'); });
    }, { threshold: 0.15 });
    document.querySelectorAll('.reveal').forEach(el => observer.observe(el));
    return () => observer.disconnect();
  }, []);

  const btnPrimary = {
    padding: '12px 24px', borderRadius: 10, background: '#00A8E8', color: '#FFFFFF',
    fontWeight: 700, fontSize: 15, border: 'none', cursor: 'pointer',
    transition: 'all 0.2s ease', display: 'flex', alignItems: 'center', gap: 8,
    boxShadow: '0 4px 12px rgba(0,168,232,0.35)'
  };
  const btnSecondary = {
    padding: '12px 24px', borderRadius: 10, background: 'transparent', color: '#1A1A2E',
    fontWeight: 700, fontSize: 15, border: '2px solid #E2E8F0', cursor: 'pointer',
    transition: 'all 0.2s ease', display: 'flex', alignItems: 'center', gap: 8,
    ':hover': { borderColor: '#00A8E8', color: '#00A8E8' }
  };
  const btnAccent = {
    ...btnPrimary, background: '#FF6B35', boxShadow: '0 4px 12px rgba(255,107,53,0.35)'
  };

  const nav = {
    position: 'fixed', top: 0, left: 0, right: 0, zIndex: 100,
    display: 'flex', alignItems: 'center', justifyContent: 'space-between',
    padding: '16px 40px', background: 'rgba(244,247,251,0.95)', backdropFilter: 'blur(12px)',
    boxShadow: '0 1px 3px rgba(0,0,0,0.05)'
  };
  const navLinks = [
    { label: 'Features', href: '#features' },
    { label: 'How It Works', href: '#how-it-works' },
    { label: 'Pricing', href: '#pricing' },
    { label: 'FAQ', href: '#faq' },
  ];

  const features = [
    { icon: <Target size={32} color="#00A8E8" />, title: 'Smart Lead Targeting', desc: 'AI-driven discovery finds ideal partners, prospects, and collaborators based on your perfect customer profile.' },
    { icon: <Sparkles size={32} color="#FF6B35" />, title: 'Autonomous Nurturing', desc: 'Personalized multi-channel sequences run on autopilot — engaging, following up, and qualifying leads 24/7.' },
    { icon: <Zap size={32} color="#00A8E8" />, title: 'Instant Engagement', desc: 'First-response in under 60 seconds with contextual, human-sounding replies that build instant trust.' },
    { icon: <TrendingUp size={32} color="#FF6B35" />, title: 'Live Insights & Analytics', desc: 'Real-time dashboards show pipeline health, engagement scores, and conversion predictions as they happen.' },
    { icon: <Users size={32} color="#00A8E8" />, title: 'Unified Inbox & CRM', desc: 'Every conversation, every lead, every status — all synced to your favorite tools including HubSpot, Slack, and Salesforce.' },
    { icon: <Shield size={32} color="#FF6B35" />, title: 'AI Diligence & Ethics', desc: 'Built-in compliance checks ensure every outreach respects privacy laws, best practices, and your brand values.' },
  ];

  const stats = [
    { value: '10x', label: 'More Qualified Leads' },
    { value: '54hrs', label: 'Saved Per Week' },
    { value: '12%', label: 'Avg. Conversion Lift' },
    { value: '24/7', label: 'Autonomous Nurturing' },
  ];

  const pricingPlans = [
    { name: 'Starter', price: '$49', per: '/month', desc: 'For solo founders testing automated outreach', features: ['500 AI-assisted leads/month', 'Basic autopilot sequences', 'Email & in-app support'], accent: false },
    { name: 'Growth', price: '$99', per: '/month', desc: 'For growing teams ready to scale pipeline', features: ['5,000 AI-assisted leads/month', 'Full autonomous nurturing', 'Advanced CRM integrations', 'Priority support'], accent: true, popular: true },
    { name: 'Scale', price: '$199', per: '/month', desc: 'For operations with multi-channel needs', features: ['Unlimited AI-assisted leads', 'Multi-channel (LinkedIn, Email, SMS)', 'Analytics & custom dashboards', 'Dedicated success manager'], accent: false },
  ];

  const steps = [
    { num: '01', title: 'Connect Your Channels', desc: 'Link your inbox, LinkedIn, and CRM in under 3 minutes. We guide you through setup with pre-built templates.', icon: <Plug size={26} /> },
    { num: '02', title: 'Define Your Audience', desc: 'Describe your ideal client or let our AI suggest personas based on your product and industry.', icon: <Search size={26} /> },
    { num: '03', title: 'Launch Autopilot', desc: 'Set goals and click Activate. SocialQ handles list building, outreach, follow-ups, and qualification around the clock.', icon: <Zap size={26} /> },
    { num: '04', title: 'Watch Your Pipeline Grow', desc: 'Monitor live results, review AI-written conversations, and receive hot leads the moment they engage.', icon: <TrendingUp size={26} /> },
  ];

  const testimonials = [
    { name: 'Sarah Chen', role: 'Founder, Bloomly', quote: 'SocialQ turned our cold outreach into a warm, automated pipeline. We stopped chasing and started closing — it genuinely feels like a growth team on autopilot.', stars: 5, avatar: 'SC' },
    { name: 'Marcus Johnson', role: 'Head of Sales, Loopify', quote: 'The AI\'s nurturing sequences are scary good. We see engagement rates 3x higher than our manual campaigns. The ROI was obvious within the first month.', stars: 5, avatar: 'MJ' },
    { name: 'Elena Rodriguez', role: 'CMO, Craftful', quote: 'Finally, a tool that doesn\'t sound robotic. SocialQ\'s tone feels human, personal, and on-brand. Our calendar is full of qualified meetings, all from AI-nurtured inbound.', stars: 5, avatar: 'ER' },
  ];

  const pricing = (plan, index) => (
    <div key={index} style={{
      background: plan.accent ? 'linear-gradient(145deg, #00A8E8, #0077B6)' : '#FFFFFF',
      color: plan.accent ? '#FFFFFF' : '#1A1A2E',
      borderRadius: 20, padding: '32px 28px', flex: 1, minWidth: 260, maxWidth: 320,
      boxShadow: plan.accent ? '0 12px 40px rgba(0,168,232,0.30)' : '0 2px 12px rgba(0,0,0,0.06)',
      border: typeof plan.accent === 'undefined' ? '1px solid #E2E8F0' : 'none',
      position: 'relative', display: 'flex', flexDirection: 'column',
      transition: 'transform 0.2s ease', cursor: 'default',
    }}>
      {plan.popular && (
        <div style={{ position: 'absolute', top: -14, left: '50%', transform: 'translateX(-50%)', background: '#FF6B35', color: '#FFFFFF', padding: '4px 16px', borderRadius: 20, fontSize: 12, fontWeight: 700, letterSpacing: 0.5 }}>
          MOST POPULAR
        </div>
      )}
      <h3 style={{ margin: 0, fontSize: 20, fontWeight: 700 }}>{plan.name}</h3>
      <p style={{ fontSize: 14, opacity: 0.7, marginTop: 8, minHeight: 40 }}>{plan.desc}</p>
      <div style={{ display: 'flex', alignItems: 'baseline', gap: 4, marginTop: 8 }}>
        <span style={{ fontSize: 42, fontWeight: 900 }}>{plan.price}</span>
        <span style={{ opacity: 0.6, fontSize: 14 }}>{plan.per}</span>
      </div>
      <div style={{ marginTop: 24, display: 'flex', flexDirection: 'column', gap: 12, flex: 1 }}>
        {(plan.features || []).map((f, i) => (
          <div key={i} style={{ display: 'flex', alignItems: 'center', gap: 8, fontSize: 14 }}>
            <CheckCircle2 size={18} color={plan.accent ? '#FFE3D6' : '#00A8E8'} />
            <span>{f}</span>
          </div>
        ))}
      </div>
      <button
        onClick={onGetStarted}
        style={{
          marginTop: 28, padding: '14px', borderRadius: 12,
          border: 'none', fontWeight: 700, fontSize: 15, cursor: 'pointer',
          background: plan.accent ? '#FFFFFF' : 'linear-gradient(145deg, #00A8E8, #0077B6)',
          color: plan.accent ? '#0077B6' : '#FFFFFF',
          boxShadow: '0 4px 12px rgba(0,0,0,0.1)', transition: 'transform 0.2s ease, box-shadow 0.2s ease',
        }}
        onMouseEnter={e => e.currentTarget.style.transform = 'translateY(-2px)'}
        onMouseLeave={e => e.currentTarget.style.transform = 'translateY(0)'}
      >
        Get Started
      </button>
    </div>
  );

  return (
    <div style={{ minHeight: '100vh', background: '#F4F7FB', color: '#1A1A2E', overflowX: 'hidden', position: 'relative' }}>
      {/* NAVIGATION */}
      <header style={nav}>
        <div style={{ display: 'flex', alignItems: 'center', gap: 10, cursor: 'pointer' }}>
          <div style={{ width: 36, height: 36, borderRadius: 10, background: 'linear-gradient(145deg, #00A8E8, #0077B6)', display: 'flex', alignItems: 'center', justifyContent: 'center' }}>
            <Zap size={20} color="#FFFFFF" />
          </div>
          <span style={{ fontSize: 22, fontWeight: 800, letterSpacing: -0.5 }}>SocialQ</span>
        </div>
        <nav style={{ display: 'flex', gap: 28, alignItems: 'center', flex: 1, maxWidth: 500, justifyContent: 'center' }}>
          {(navLinks || []).map(l => (
            <a key={l.label} href={l.href} style={{ color: '#475569', textDecoration: 'none', fontSize: 14, fontWeight: 600, transition: 'color 0.2s ease' }}
               onMouseEnter={e => e.currentTarget.style.color = '#00A8E8'}
               onMouseLeave={e => e.currentTarget.style.color = '#475569'}>
              {l.label}
            </a>
          ))}
        </nav>
        <div style={{ display: 'flex', gap: 12, alignItems: 'center' }}>
          <button onClick={onLogin} style={{ background: 'transparent', border: 'none', color: '#1A1A2E', fontWeight: 600, cursor: 'pointer', fontSize: 14, padding: '10px 18px', transition: 'all 0.2s ease' }}>
            Log in
          </button>
          <button onClick={onGetStarted} style={btnPrimary}>
            Get Started <ArrowRight size={18} />
          </button>
          <button onClick={() => setMenuOpen(!menuOpen)} style={{ display: 'none', '@media (max-width: 768px)': { display: 'block' }, background: 'none', border: 'none', cursor: 'pointer' }}>
            {menuOpen ? <X size={28} color="#1A1A2E" /> : <Menu size={28} color="#1A1A2E" />}
          </button>
        </div>
      </header>

      {/* MOBILE MENU */}
      {menuOpen && (
        <div style={{ position: 'fixed', top: 70, left: 0, right: 0, background: '#FFFFFF', boxShadow: '0 20px 40px rgba(0,0,0,0.1)', padding: 24, zIndex: 99 }}>
          {(navLinks || []).map(l => (
            <a key={l.label} href={l.href} onClick={() => setMenuOpen(false)} style={{ display: 'block', color: '#1A1A2E', textDecoration: 'none', padding: '14px 0', fontSize: 16, fontWeight: 600, borderBottom: '1px solid #F1F5F9' }}>
              {l.label}
            </a>
          ))}
          <div style={{ display: 'flex', gap: 12, marginTop: 20 }}>
            <button onClick={onLogin} style={{ flex: 1, padding: '14px', border: '2px solid #E2E8F0', background: 'transparent', borderRadius: 10, color: '#1A1A2E', fontWeight: 700, cursor: 'pointer' }}>Log in</button>
            <button onClick={onGetStarted} style={{ flex: 1, ...(btnPrimary || []), justifyContent: 'center' }}>Get Started</button>
          </div>
        </div>
      )}

      {/* HERO SECTION */}
      <section style={{
        paddingTop: 120, paddingBottom: 80, paddingInline: 40,
        maxWidth: 1200, margin: '0 auto', display: 'flex', flexDirection: 'column', alignItems: 'center', textAlign: 'center',
      }}>
        <div className="animate-fade-up" style={{ display: 'flex', flexDirection: 'column', alignItems: 'center', gap: 20 }}>
          <div style={{ display: 'flex', gap: 6, padding: '6px 18px', borderRadius: 20, background: 'rgba(0,168,232,0.08)', alignItems: 'center', fontSize: 13, fontWeight: 600, color: '#0077B6' }}>
            <Sparkles size={15} color="#FF6B35" />
            <span>Autonomous Lead-Generation Agent</span>
          </div>
          <h1 style={{ fontSize: '3.4em', lineHeight: 1.15, margin: 0, maxWidth: 760, letterSpacing: -1, fontWeight: 900, background: 'linear-gradient(130deg, #1A1A2E 0%, #0077B6 60%, #00A8E8 100%)', WebkitBackgroundClip: 'text', WebkitTextFillColor: 'transparent' }}>
            Find &amp; Nurture Dream Clients — On Autopilot
          </h1>
          <p style={{ maxWidth: 640, fontSize: 18, lineHeight: 1.6, color: '#475569', margin: 0 }}>
            Your AI-powered growth agent hunts down ideal leads, runs personal, timely outreach,
            and builds real relationships around the clock — so you close deals while focusing on what matters.
          </p>
          <div style={{ display: 'flex', gap: 16, marginTop: 16 }}>
            <button onClick={onGetStarted} style={btnPrimary}>
              Start Automating Free <ArrowRight size={18} />
            </button>
            <button onClick={onGetStarted} style={btnSecondary}>
              <PlayCircle size={20} color="#FF6B35" /> See How It Works
            </button>
          </div>
          <div style={{ display: 'flex', gap: 20, marginTop: 20, fontSize: 13, color: '#64748B', alignItems: 'center' }}>
            <span style={{ display: 'flex', alignItems: 'center', gap: 6 }}><CheckCircle2 size={16} color="#00A8E8" /> No credit card required</span>
            <span style={{ display: 'flex', alignItems: 'center', gap: 6 }}><CheckCircle2 size={16} color="#00A8E8" /> 14-day free trial</span>
            <span style={{ display: 'flex', alignItems: 'center', gap: 6 }}><CheckCircle2 size={16} color="#00A8E8" /> Cancel anytime</span>
          </div>
        </div>

        {/* STATS BAR */}
        <div className="stagger animate-fade-up" style={{ display: 'flex', gap: 60, marginTop: 40, fontWeight: 700, justifyContent: 'center', flexWrap: 'wrap' }}>
          {(stats || []).map((s, i) => (
            <div key={i} style={{ textAlign: 'center' }}>
              <div style={{ fontSize: 40, fontWeight: 900, color: '#00A8E8' }}>{s.value}</div>
              <div style={{ fontSize: 14, fontWeight: 500, color: '#64748B' }}>{s.label}</div>
            </div>
          ))}
        </div>

        {/* DASHBOARD PREVIEW */}
        <div className="animate-float" style={{
          position: 'relative', marginTop: 60, borderRadius: 20, overflow: 'hidden',
          boxShadow: '0 12px 40px rgba(0,0,0,0.12), 0 0 0 1px rgba(0,168,232,0.15)',
          maxWidth: 800, width: '100%',
        }}>
          <div style={{ background: '#FFFFFF', padding: 24 }}>
            <div style={{ display: 'flex', justifyContent: 'space-between', alignItems: 'center', marginBottom: 20 }}>
              <div>
                <div style={{ fontSize: 18, fontWeight: 800, color: '#1A1A2E' }}>Growth Overview</div>
                <div style={{ fontSize: 13, color: '#64748B' }}>Real-time pipeline (last 30 days)</div>
              </div>
              <div style={{ display: 'flex', gap: 10 }}>
                <div style={{ background: '#F1F5F9', padding: '8px 14px', borderRadius: 20, fontSize: 13, fontWeight: 600, color: '#475569' }}>This week</div>
                <div style={{ background: 'rgba(255,107,53,0.1)', padding: '8px 14px', borderRadius: 20, fontSize: 13, fontWeight: 600, color: '#FF6B35' }}>All time</div>
              </div>
            </div>
            <div style={{ display: 'flex', gap: 10, height: 180 }}>
              <div style={{ flex: 1, display: 'flex', alignItems: 'flex-end', gap: 6 }}>
                {[40, 65, 50, 90, 75, 110, 95].map((h, i) => (
                  <div key={i} style={{ flex: 1, borderRadius: '8px 8px 0 0', background: 'linear-gradient(180deg, #00A8E8, #0077B6)', height: `${h}%`, opacity: 0.8 }} />
                ))}
              </div>
              <div style={{ flex: 0.4, display: 'flex', alignItems: 'flex-end', gap: 6 }}>
                {[60, 95, 80, 120, 105, 140].map((h, i) => (
                  <div key={i} style={{ flex: 1, borderRadius: '8px 8px 0 0', background: 'linear-gradient(180deg, #FFB08D, #FF6B35)', height: `${h}%`, opacity: 0.9 }} />
                ))}
              </div>
            </div>
            <div style={{ display: 'flex', gap: 16, marginTop: 16, fontSize: 13 }}>
              <div style={{ display: 'flex', alignItems: 'center', gap: 6 }}><div style={{ width: 12, height: 12, borderRadius: 3, background: '#00A8E8' }} /> New leads</div>
              <div style={{ display: 'flex', alignItems: 'center', gap: 6 }}><div style={{ width: 12, height: 12, borderRadius: 3, background: '#FF6B35' }} /> Qualified meetings</div>
            </div>
          </div>
        </div>
      </section>

      {/* LOGO STRIP */}
      <div style={{ paddingBlock: 30, borderBottom: '1px solid #E2E8F0', display: 'flex', justifyContent: 'center', gap: 40, fontSize: 14, color: '#94A3B8', fontWeight: 600, letterSpacing: 0.5 }}>
        <span>TRUSTED BY OPERATORS AT</span>
        <span style={{ fontStyle: 'italic', fontSize: 16 }}>Curio</span>
      </div>

      {/* FEATURES SECTION */}
      <section id="features" style={{ padding: '80px 40px', maxWidth: 1100, margin: '0 auto' }}>
        <div style={{ textAlign: 'center', marginBottom: 60 }}>
          <div style={{ fontSize: 13, fontWeight: 800, letterSpacing: 1, color: '#00A8E8', textTransform: 'uppercase' }}>Platform capabilities</div>
          <h2 style={{ fontSize: 40, fontWeight: 900, letterSpacing: -0.5, marginTop: 8, marginBottom: 12 }}>Everything You Need to Close Clients</h2>
          <p style={{ maxWidth: 560, margin: '0 auto', color: '#64748B', fontSize: 17 }}>Six core modules work together as your always-on growth engine.</p>
        </div>
        <div className="reveal" style={{ display: 'flex', flexWrap: 'wrap', gap: 24, justifyContent: 'center' }}>
          {(features || []).map((f, i) => (
            <div key={i} style={{
              background: '#FFFFFF', borderRadius: 18, padding: '28px 24px', width: 'calc(33.33% - 16px)', minWidth: 280,
              boxShadow: '0 2px 8px rgba(0,0,0,0.05)', flex: '1', transition: 'transform 0.2s ease, boxShadow 0.2s ease',
              display: 'flex', flexDirection: 'column', gap: 14, cursor: 'default',
            }}
              onMouseEnter={e => { e.currentTarget.style.transform = 'translateY(-4px)'; e.currentTarget.style.boxShadow = '0 8px 20px rgba(0,0,0,0.08)'; }}
              onMouseLeave={e => { e.currentTarget.style.transform = 'translateY(0)'; e.currentTarget.style.boxShadow = '0 2px 8px rgba(0,0,0,0.05)'; }}>
              <div style={{ width: 56, height: 56, borderRadius: 14, background: `${i % 2 === 0 ? 'rgba(0,168,232,0.08)' : 'rgba(255,107,53,0.08)'}`, display: 'flex', alignItems: 'center', justifyContent: 'center' }}>
                {f.icon}
              </div>
              <div>
                <h3 style={{ fontSize: 17, fontWeight: 800, margin: 0, color: '#1A1A2E' }}>{f.title}</h3>
                <p style={{ fontSize: 14, color: '#64748B', lineHeight: 1.55, marginTop: 6, marginBottom: 0 }}>{f.desc}</p>
              </div>
              <div style={{ marginTop: 'auto' }}>
                <a href="#" onClick={(e) => e.preventDefault()} style={{ fontSize: 14, fontWeight: 600, color: '#00A8E8', textDecoration: 'none', display: 'flex', alignItems: 'center', gap: 4 }}>
                  Learn more <ChevronRight size={16} />
                </a>
              </div>
            </div>
          ))}
        </div>
      </section>

      {/* HOW IT WORKS */}
      <section id="how-it-works" style={{ padding: '80px 40px', background: '#FFFFFF' }}>
        <div style={{ maxWidth: 1100, margin: '0 auto' }}>
          <div style={{ textAlign: 'center', marginBottom: 60 }}>
            <div style={{ fontSize: 13, fontWeight: 800, letterSpacing: 1, color: '#FF6B35', textTransform: 'uppercase' }}>How it works</div>
            <h2 style={{ fontSize: 40, fontWeight: 900, letterSpacing: -0.5, marginTop: 8, marginBottom: 12 }}>Set Up in Minutes. Run Forever.</h2>
            <p style={{ maxWidth: 560, margin: '0 auto', color: '#64748B', fontSize: 17 }}>Our guided onboarding walks you through the quick start flow — most teams go live in under 5 minutes.</p>
          </div>
          <div className="reveal" style={{ display: 'grid', gridTemplateColumns: 'repeat(auto-fit, minmax(200px, 1fr))', gap: 24 }}>
            {(steps || []).map((s, i) => (
              <div key={i} style={{ textAlign: 'left', position: 'relative', padding: '24px', background: '#F8FAFC', borderRadius: 16 }}>
                <div style={{ display: 'flex', alignItems: 'center', justifyContent: 'flex-start', marginBottom: 16 }}>
                  <div style={{ width: 48, height: 48, borderRadius: 12, background: i % 2 === 0 ? 'rgba(0,168,232,0.1)' : 'rgba(255,107,53,0.1)', color: i % 2 === 0 ? '#00A8E8' : '#FF6B35', display: 'flex', alignItems: 'center', justifyContent: 'center' }}>
                    {s.icon}
                  </div>
                  <span style={{ marginLeft: 'auto', fontSize: 38, fontWeight: 900, color: '#E2E8F0' }}>{s.num}</span>
                </div>
                <h3 style={{ fontSize: 17, fontWeight: 800, color: '#1A1A2E', marginTop: 0 }}>{s.title}</h3>
                <p style={{ fontSize: 14, color: '#64748B', lineHeight: 1.6, marginBottom: 0 }}>{s.desc}</p>
              </div>
            ))}
          </div>
        </div>
      </section>

      {/* PRODUCT DARK STRIP */}
      <section style={{ padding: '70px 40px', background: 'linear-gradient(145deg, #0B1120, #1A1A2E)', color: '#FFFFFF', textAlign: 'center' }}>
        <div style={{ maxWidth: 900, margin: '0 auto' }}>
          <h2 style={{ fontSize: 34, fontWeight: 900, letterSpacing: -0.5, marginTop: 0 }}>"It's like having a tireless growth teammate who never sleeps."</h2>
          <p style={{ fontSize: 18, opacity: 0.7, marginTop: 10 }}>— Alex Rivera, VP Growth at Northwind</p>
          <button onClick={onGetStarted} style={{ ...btnAccent, marginTop: 30, padding: '16px 36px', fontSize: 16 }}>
            Activate My Autopilot <ArrowRight size={20} />
          </button>
        </div>
      </section>

      {/* PRICING */}
      <section id="pricing" style={{ padding: '80px 40px', maxWidth: 1100, margin: '0 auto' }}>
        <div style={{ textAlign: 'center', marginBottom: 60 }}>
          <div style={{ fontSize: 13, fontWeight: 800, letterSpacing: 1, color: '#00A8E8', textTransform: 'uppercase' }}>Pricing</div>
          <h2 style={{ fontSize: 40, fontWeight: 900, letterSpacing: -0.5, marginTop: 8, marginBottom: 12 }}>Simple. When You Win, We Win.</h2>
          <p style={{ maxWidth: 560, margin: '0 auto', color: '#64748B', fontSize: 17 }}>Every plan includes automation, integrations, and analytics. No per-seat fees, no silly overages.</p>
        </div>
        <div className="reveal" style={{ display: 'flex', gap: 24, justifyContent: 'center', flexWrap: 'wrap', alignItems: 'stretch' }}>
          {(pricingPlans || []).map((plan, i) => pricing(plan, i))}
        </div>
        <div style={{ textAlign: 'center', marginTop: 40, fontSize: 15, color: '#64748B' }}>
          <span>All plans include 14-day free trial · Cancel anytime · <a href="#" style={{ color: '#00A8E8', cursor: 'pointer' }}>Talk to sales</a></span>
        </div>
      </section>

      {/* TESTIMONIALS */}
      <section style={{ padding: '60px 40px', background: '#EDF2F7', }}>
        <div style={{ maxWidth: 1100, margin: '0 auto' }}>
          <div style={{ textAlign: 'center', marginBottom: 50 }}>
            <div style={{ fontSize: 13, fontWeight: 800, letterSpacing: 1, color: '#FF6B35', textTransform: 'uppercase' }}>Loved by teams</div>
            <h2 style={{ fontSize: 34, fontWeight: 900, letterSpacing: -0.5, marginTop: 8 }}>Real Results from Real Customers</h2>
          </div>
          <div className="reveal" style={{ display: 'flex', gap: 20, justifyContent: 'center', flexWrap: 'wrap' }}>
            {(testimonials || []).map((t, i) => (
              <div key={i} style={{ background: '#FFFFFF', borderRadius: 16, padding: '24px 28px', width: 'calc(33.33% - 14px)', minWidth: 280, boxShadow: '0 2px 8px rgba(0,0,0,0.05)', display: 'flex', flexDirection: 'column' }}>
                <div style={{ display: 'flex', gap: 3, marginBottom: 12 }}>{[...Array(t.stars || 0)].map((_, si) => <Star key={si} size={18} fill="#FFB800" color="#FFB800" />)}</div>
                <p style={{ fontSize: 15, lineHeight: 1.6, color: '#334155', flex: 1, fontStyle: 'italic' }}>"{t.quote}"</p>
                <div style={{ display: 'flex', alignItems: 'center', gap: 12, marginTop: 18 }}>
                  <div style={{ width: 42, height: 42, borderRadius: 50, background: i % 2 === 0 ? '#00A8E8' : '#FF6B35', color: '#FFFFFF', display: 'flex', alignItems: 'center', justifyContent: 'center', fontWeight: 800, fontSize: 16 }}>{t.avatar}</div>
                  <div>
                    <div style={{ fontWeight: 700, fontSize: 15 }}>{t.name}</div>
                    <div style={{ fontSize: 13, color: '#64748B' }}>{t.role}</div>
                  </div>
                </div>
              </div>
            ))}
          </div>
        </div>
      </section>

      {/* FAQ LIGHTHOUSE */}
      <section id="faq" style={{ padding: '40px 40px', maxWidth: 750, margin: '0 auto' }}>
        <div style={{ textAlign: 'center', marginBottom: 30 }}>
          <h2 style={{ fontSize: 32, fontWeight: 900, letterSpacing: -0.5 }}>Before You Start...</h2>
        </div>
        {[
          { q: 'Is this really "autonomous"? Do I need to be online?', a: 'Yes and no. You set the guardrails and goals, approve key messages once, and SocialQ manages the rest — entirely unaffected by your working hours. It adapts tone, timing, and next-step logic per lead. You can also jump in anytime.' },
          { q: 'Will it sound spammy? Will my contacts get annoyed?', a: 'Never. We use strict frequency caps, personalization variables, and AI ethics checks. You approve all templates before launch, and we automatically suppress replies and opt-outs, ensuring a professional, respectful experience every time.' },
          { q: 'How fast will I see results?', a: 'Most clients see measurable impact within the first 2 weeks: 20-30% positive reply rate, meaningful conversations and opportunities. Full pipeline velocity improves by month 2-3 once the AI learns your best fits.' },
          { q: 'How does this integrate with my existing stack?', a: 'Native integrations with HubSpot, Salesforce, Slack, Gmail, Outlook, LinkedIn, and 40+ tools. Plus an open API and Zapier, and our growth concierge team will help you set everything up on day one.' },
          { q: 'What if I outgrow the automated experience?', a: 'Layered support is baked in. Whenever you need a human, you can attach them to any ongoing conversation. Premium plans even include a dedicated success manager to continuously tune your AI.' },
        ].map((f, i) => (
          <FaqItem key={i} q={f.q} a={f.a} />
        ))}
      </section>

      {/* FINAL CTA */}
      <section style={{ padding: '60px 40px', textAlign: 'center', background: 'linear-gradient(145deg, #00A8E8, #0077B6)' }}>
        <div style={{ display: 'flex', flexDirection: 'column', alignItems: 'center', gap: 20 }}>
          <h2 style={{ fontSize: 40, fontWeight: 900, color: '#FFFFFF', letterSpacing: -0.5, margin: 0 }}>Your Future Clients Are Waiting.</h2>
          <p style={{ fontSize: 18, color: 'rgba(255,255,255,0.85)', maxWidth: 600, margin: 0 }}>Start the 14-day free trial today. No credit card, no commitment — just your pipeline growing on autopilot.</p>
          <button onClick={onGetStarted} style={{ ...btnAccent, padding: '16px 36px', fontSize: 16, boxShadow: '0 8px 25px rgba(0,0,0,0.2)' }}>
            Start My Free Trial <ArrowRight size={20} />
          </button>
          <button onClick={onLogin} style={{ background: 'none', border: 'none', color: '#FFFFFF', fontSize: 14, cursor: 'pointer', textDecoration: 'underline', marginTop: 8 }}>
            Have an account? Log in
          </button>
        </div>
      </section>

      {/* FOOTER */}
      <footer style={{ padding: '50px 40px', background: '#0B1120', color: '#E2E8F0' }}>
        <div style={{ maxWidth: 1100, margin: '0 auto', display: 'grid', gridTemplateColumns: 'repeat(auto-fit, minmax(200px, 1fr))', gap: 40 }}>
          <div>
            <div style={{ display: 'flex', alignItems: 'center', gap: 8, marginBottom: 16 }}>
              <div style={{ width: 30, height: 30, borderRadius: 8, background: 'linear-gradient(145deg, #00A8E8, #0077B6)', display: 'flex', alignItems: 'center', justifyContent: 'center' }}>
                <Zap size={16} color="#FFFFFF" />
              </div>
              <span style={{ fontWeight: 800, fontSize: 20 }}>SocialQ</span>
            </div>
            <p style={{ fontSize: 14, lineHeight: 1.6, maxWidth: 320, color: '#94A3B8' }}>Your autonomous growth partner for finding leads, building trust, and winning the deals you deserve.</p>
            <div style={{ display: 'flex', gap: 8, marginTop: 16 }}>
              {['X', 'in', 'f', '▶'].map((icon, i) => (
                <div key={i} style={{ width: 36, height: 36, borderRadius: 8, background: '#1E293B', display: 'flex', alignItems: 'center', justifyContent: 'center', cursor: 'pointer', color: '#64748B', fontSize: 14, fontWeight: 700, transition: 'all 0.2s ease' }}
                     onMouseEnter={e => { e.currentTarget.style.background = '#00A8E8'; e.currentTarget.style.color = '#FFFFFF'; }}
                     onMouseLeave={e => { e.currentTarget.style.background = '#1E293B'; e.currentTarget.style.color = '#64748B'; }}>
                  {icon}
                </div>
              ))}
            </div>
          </div>
          {[
            { title: 'Product', items: ['Features', 'Integrations', 'Pricing', 'Changelog', 'Roadmap'] },
            { title: 'Company', items: ['About us', 'Careers', 'Blog', 'Press', 'Contact'] },
            { title: 'Resources', items: ['Help center', 'API docs', 'Community', 'Webinars', 'Trust'] },
          ].map((col, i) => (
            <div key={i}>
              <h4 style={{ color: '#FFFFFF', margin: '0 0 14px', fontSize: 14, fontWeight: 700, letterSpacing: 0.5, textTransform: 'uppercase' }}>{col.title}</h4>
              {(col.items || []).map((item, j) => (
                <a key={j} href="#" onClick={e => e.preventDefault()} style={{ display: 'block', color: '#94A3B8', textDecoration: 'none', fontSize: 14, padding: '6px 0', transition: 'color 0.2s ease' }}
                   onMouseEnter={e => e.currentTarget.style.color = '#00A8E8'}
                   onMouseLeave={e => e.currentTarget.style.color = '#94A3B8'}>
                  {item}
                </a>
              ))}
            </div>
          ))}
        </div>
        <div style={{ borderTop: '1px solid #1E293B', marginTop: 40, paddingTop: 30, fontSize: 13, color: '#64748B', textAlign: 'center' }}>
          © 2024 SocialQ, Inc. All rights reserved. · <a href="#" style={{ color: '#64748B' }}>Privacy</a> · <a href="#" style={{ color: '#64748B' }}>Terms</a>
        </div>
      </footer>
    </div>
  );
};

function FaqItem({ q, a }) {
  const [open, setOpen] = useState(false);
  return (
    <div style={{ borderBottom: '1px solid #E2E8F0' }}>
      <button
        onClick={() => setOpen(!open)}
        style={{
          display: 'flex', alignItems: 'center', justifyContent: 'space-between', width: '100%',
          padding: '18px 0', background: 'transparent', border: 'none', cursor: 'pointer', textAlign: 'left', color: '#1A1A2E',
        }}>
        <span style={{ fontWeight: 700, fontSize: 16 }}>{q}</span>
        <span style={{ color: '#00A8E8', fontSize: 22 }}>{open ? '−' : '+'}</span>
      </button>
      {open && (
        <p style={{ padding: '0 0 18px', fontSize: 14, lineHeight: 1.65, color: '#475569', margin: 0 }}>
          {a}
        </p>
      )}
    </div>
  );
}

function ProductApp({ user, onLogout }) {
  const [view, setView] = useState('overview');
  const [sidebarOpen, setSidebarOpen] = useState(false);

  const [leads, setLeads] = useState([
    { id: 1, name: 'Sarah Chen', company: 'Bloomly', stage: 'Nurturing', value: 12000, lastContact: '2h ago', status: 'Warm' },
    { id: 2, name: 'Marcus Johnson', company: 'Loopify', stage: 'Qualified', value: 34000, lastContact: '1d ago', status: 'Hot' },
    { id: 3, name: 'Elena Rodriguez', company: 'Craftful', stage: 'New', value: 8000, lastContact: '3h ago', status: 'New' },
    { id: 4, name: 'David Kim', company: 'Northwind', stage: 'Proposal', value: 27000, lastContact: '30m ago', status: 'Hot' },
    { id: 5, name: 'Lisa Patel', company: 'Craftful', stage: 'Nurturing', value: 15000, lastContact: '5h ago', status: 'Warm' },
    { id: 6, name: 'Tom Becker', company: 'Loopify', stage: 'New', value: 9500, lastContact: 'Just now', status: 'New' },
  ]);

  const [conversations, setConversations] = useState([
    { id: 1, lead: 'David Kim', preview: 'Thanks! I\'d love to see a demo of the automation flow.', time: '2m', unread: true, channel: 'Email' },
    { id: 2, lead: 'Sarah Chen', preview: 'Sent you the deck — let me know what you think!', time: '4m', unread: true, channel: 'LinkedIn' },
    { id: 3, lead: 'Tom Becker', preview: 'Hi! I saw your post about AI sales tools and thought...', time: '12m', unread: false, channel: 'Email' },
    { id: 4, lead: 'Marcus Johnson', preview: 'The integration with our CRM looks straightforward. When can we...', time: '1h', unread: false, channel: 'LinkedIn' },
  ]);

  const [automations, setAutomations] = useState([
    { id: 1, name: 'New Lead Nurture', status: 'Active', runs: 248, success: 92, nextRun: 'In 2h' },
    { id: 2, name: 'Follow-Up Sequence B', status: 'Active', runs: 156, success: 87, nextRun: 'In 5h' },
    { id: 3, name: "Win-Back Campaign", status: 'Paused', runs: 64, success: 78, nextRun: '—' },
    { id: 4, name: 'A/B Test Subject Lines', status: 'Active', runs: 312, success: 91, nextRun: 'In 30m' },
  ]);

  const [messages, setMessages] = useState([
    { role: 'ai', text: "I've found 3 new leads matching your ideal customer profile. Want me to start outreach?" },
    { role: 'user', text: 'Yes, please — prioritize the ones from SaaS companies.' },
    { role: 'ai', text: "Done! 2 leads from SaaS companies are now in the 'New' stage. I've personalized each first message based on their recent LinkedIn activity." },
  ]);

  const [campaigns, setCampaigns] = useState([
    { name: 'Summer Outreach', leads: 1240, replied: 186, meetings: 24, status: 'Live' },
    { name: 'Reactivation', leads: 842, replied: 98, meetings: 11, status: 'Live' },
    { name: 'Enterprise Push', leads: 310, replied: 42, meetings: 8, status: 'Draft' },
  ]);

  const [messageInput, setMessageInput] = useState('');
  const [activeChat, setActiveChat] = useState(1);
  const [showProfileMenu, setShowProfileMenu] = useState(false);

  const stats = [
    { label: 'Total Leads', value: '2,847', change: '+12.5%', icon: <Users size={18} color="#818cf8" /> },
    { label: 'Meetings Booked', value: '86', change: '+8.2%', icon: <Calendar size={18} color="#34d399" /> },
    { label: 'Reply Rate', value: '23.4%', change: '+3.1%', icon: <MessageCircle size={18} color="#fbbf24" /> },
    { label: 'Pipeline Value', value: '$412K', change: '+18.9%', icon: <TrendingUp size={18} color="#f472b6" /> },
  ];

  const activity = [
    { icon: <Search size={14} color="#818cf8" />, text: 'AI discovered 12 new leads matching your ICP', time: '5m ago' },
    { icon: <MessageCircle size={14} color="#34d399" />, text: 'David Kim replied to your LinkedIn outreach', time: '32m ago' },
    { icon: <Calendar size={14} color="#fbbf24" />, text: 'Meeting booked: Marcus Johnson — Demo call', time: '1h ago' },
    { icon: <TrendingUp size={14} color="#f472b6" />, text: 'Pipeline value crossed $400K milestone', time: '3h ago' },
  ];

  const sendMessage = () => {
    if (!messageInput.trim()) return;
    setMessages([...(messages || []), { role: 'user', text: messageInput }]);
    setMessageInput('');
    setTimeout(() => {
      setMessages(m => [...(m || []), { role: 'ai', text: "Great! I'll handle that now and keep you posted on progress." }]);
    }, 800);
  };

  const getStageColor = (stage) => {
    const colors = { 'New': '#818cf8', 'Nurturing': '#fbbf24', 'Qualified': '#34d399', 'Proposal': '#f472b6' };
    return colors[stage] || '#818cf8';
  };

  const getStatusColor = (status) => {
    const colors = { 'Hot': '#ef4444', 'Warm': '#f59e0b', 'New': '#818cf8' };
    return colors[status] || '#818cf8';
  };

  const navItems = [
    { id: 'overview', label: 'Overview', icon: <TrendingUp size={18} /> },
    { id: 'leads', label: 'Leads', icon: <Users size={18} />, badge: leads.length },
    { id: 'conversations', label: 'Conversations', icon: <MessageCircle size={18} />, badge: 2 },
    { id: 'automations', label: 'Automations', icon: <Zap size={18} /> },
    { id: 'campaigns', label: 'Campaigns', icon: <Target size={18} /> },
  ];

  const chartData = [42, 55, 48, 70, 65, 82, 78, 95, 88, 102, 96, 110];

  const renderOverview = () => (
    <div style={{ display: 'flex', flexDirection: 'column', gap: 24 }}>
      {/* Stats cards */}
      <div style={{ display: 'grid', gridTemplateColumns: 'repeat(auto-fit, minmax(200px, 1fr))', gap: 16 }}>
        {(stats || []).map((s, i) => (
          <div key={i} style={{ background: '#141a30', borderRadius: 14, padding: 20, border: '1px solid #232b45', display: 'flex', flexDirection: 'column', gap: 12 }}>
            <div style={{ display: 'flex', alignItems: 'center', justifyContent: 'space-between' }}>
              <div style={{ width: 36, height: 36, borderRadius: 10, background: 'rgba(99,102,241,0.1)', display: 'flex', alignItems: 'center', justifyContent: 'center' }}>{s.icon}</div>
              <span style={{ fontSize: 12, fontWeight: 700, color: '#34d399' }}>{s.change}</span>
            </div>
            <div>
              <div style={{ fontSize: 28, fontWeight: 800, letterSpacing: -0.5 }}>{s.value}</div>
              <div style={{ fontSize: 13, color: '#9aa6bd' }}>{s.label}</div>
            </div>
          </div>
        ))}
      </div>

      {/* Charts row */}
      <div style={{ display: 'grid', gridTemplateColumns: '2fr 1fr', gap: 16, marginTop: 4 }}>
        <div style={{ background: '#141a30', borderRadius: 14, padding: 20, border: '1px solid #232b45' }}>
          <div style={{ display: 'flex', justifyContent: 'space-between', alignItems: 'center', marginBottom: 16 }}>
            <div>
              <div style={{ fontSize: 16, fontWeight: 700 }}>Pipeline Growth</div>
              <div style={{ fontSize: 13, color: '#9aa6bd' }}>Leads generated per week</div>
            </div>
            <div style={{ display: 'flex', gap: 10 }}>
              {['1W', '1M', '3M'].map((p, i) => (
                <span key={i} style={{ fontSize: 12, color: i === 1 ? '#818cf8' : '#9aa6bd', fontWeight: i === 1 ? 700 : 400, cursor: 'pointer', padding: '4px 8px', borderRadius: 6, background: i === 1 ? 'rgba(99,102,241,0.1)' : 'transparent' }}>{p}</span>
              ))}
            </div>
          </div>
          <div style={{ display: 'flex', gap: 4, alignItems: 'flex-end', height: 160 }}>
            {(chartData || []).map((h, i) => (
              <div key={i} style={{ flex: 1, height: `${h}%`, borderRadius: '4px 4px 0 0', background: i % 2 === 0 ? 'rgba(99,102,241,0.7)' : 'rgba(52,211,153,0.7)', transition: 'height 0.3s ease' }} />
            ))}
          </div>
        </div>
        <div style={{ background: '#141a30', borderRadius: 14, padding: 20, border: '1px solid #232b45' }}>
          <div style={{ fontSize: 16, fontWeight: 700, marginBottom: 16 }}>Recent Activity</div>
          <div style={{ display: 'flex', flexDirection: 'column', gap: 14 }}>
            {(activity || []).map((a, i) => (
              <div key={i} style={{ display: 'flex', gap: 10, alignItems: 'flex-start' }}>
                <div style={{ width: 28, height: 28, borderRadius: 8, background: 'rgba(99,102,241,0.1)', display: 'flex', alignItems: 'center', justifyContent: 'center', flexShrink: 0 }}>{a.icon}</div>
                <div style={{ fontSize: 13 }}>
                  <div style={{ color: '#e6eaf2', lineHeight: 1.4 }}>{a.text}</div>
                  <div style={{ color: '#9aa6bd', fontSize: 12, marginTop: 2 }}>{a.time}</div>
                </div>
              </div>
            ))}
          </div>
        </div>
      </div>

      {/* Active conversations preview */}
      <div style={{ background: '#141a30', borderRadius: 14, padding: 20, border: '1px solid #232b45' }}>
        <div style={{ display: 'flex', justifyContent: 'space-between', alignItems: 'center', marginBottom: 16 }}>
          <div style={{ fontSize: 16, fontWeight: 700 }}>Active Conversations</div>
          <button onClick={() => setView('conversations')} style={{ background: 'none', border: 'none', color: '#818cf8', fontSize: 13, fontWeight: 600, cursor: 'pointer' }}>View all</button>
        </div>
        <div style={{ display: 'flex', flexDirection: 'column' }}>
          {(conversations || []).slice(0, 3).map((c, i) => (
            <div key={i} style={{ padding: '12px 0', borderBottom: i < 2 ? '1px solid #232b45' : 'none', display: 'flex', justifyContent: 'space-between', alignItems: 'center', cursor: 'pointer' }} onClick={() => setView('conversations')}>
              <div style={{ display: 'flex', alignItems: 'center', gap: 10 }}>
                <div style={{ width: 34, height: 34, borderRadius: 50, background: '#6366f1', color: '#fff', display: 'flex', alignItems: 'center', justifyContent: 'center', fontWeight: 700, fontSize: 13 }}>{c.lead.split(' ').map(n => n[0]).join('')}</div>
                <div>
                  <div style={{ fontSize: 14, fontWeight: 600 }}>{c.lead} <span style={{ fontSize: 11, color: '#9aa6bd', fontWeight: 400 }}>· {c.channel}</span></div>
                  <div style={{ fontSize: 13, color: '#9aa6bd' }}>{c.preview}</div>
                </div>
              </div>
              <div style={{ display: 'flex', alignItems: 'center', gap: 12 }}>
                <span style={{ fontSize: 12, color: '#9aa6bd' }}>{c.time}</span>
                {c.unread && <span style={{ width: 8, height: 8, borderRadius: 50, background: '#6366f1' }} />}
              </div>
            </div>
          ))}
        </div>
      </div>
    </div>
  );

  const renderLeads = () => (
    <div style={{ display: 'flex', flexDirection: 'column', gap: 16 }}>
      <div style={{ display: 'flex', justifyContent: 'space-between', alignItems: 'center', gap: 16, flexWrap: 'wrap' }}>
        <div style={{ display: 'flex', gap: 10, flex: 1, minWidth: 240 }}>
          <input placeholder="Search leads, companies..." style={{ flex: 1, padding: '10px 14px', borderRadius: 10, border: '1px solid #232b45', background: '#141a30', color: '#e6eaf2', fontSize: 14, outline: 'none' }} />
          <button style={{ padding: '10px 16px', borderRadius: 10, background: '#6366f1', color: '#fff', border: 'none', fontWeight: 600, fontSize: 13, cursor: 'pointer' }}>+ Add Lead</button>
        </div>
        <div style={{ display: 'flex', gap: 8 }}>
          {(['All', 'New', 'Warm', 'Hot', 'Qualified'] || []).map((f, i) => (
            <button key={i} style={{ padding: '8px 14px', borderRadius: 8, background: i === 0 ? '#6366f1' : 'transparent', color: i === 0 ? '#fff' : '#9aa6bd', border: `1px solid ${i === 0 ? '#6366f1' : '#232b45'}`, fontSize: 13, fontWeight: 600, cursor: 'pointer' }}>{f}</button>
          ))}
        </div>
      </div>
      <div style={{ background: '#141a30', borderRadius: 14, border: '1px solid #232b45', overflow: 'hidden' }}>
        <table style={{ width: '100%', borderCollapse: 'collapse', fontSize: 14 }}>
          <thead>
            <tr style={{ background: '#0f1424' }}>
              {['Lead', 'Company', 'Stage', 'Value', 'Status', 'Last Contact', ''] .map((h, i) => (
                <th key={i} style={{ padding: '14px 16px', textAlign: 'left', fontSize: 12, fontWeight: 700, color: '#9aa6bd', textTransform: 'uppercase', letterSpacing: 0.5, borderBottom: '1px solid #232b45' }}>{h}</th>
              ))}
            </tr>
          </thead>
          <tbody>
            {(leads || []).map((l, i) => (
              <tr key={i} style={{ borderBottom: i < leads.length - 1 ? '1px solid #1a2340' : 'none', cursor: 'pointer' }}>
                <td style={{ padding: '14px 16px', fontWeight: 600 }}>
                  <div style={{ display: 'flex', alignItems: 'center', gap: 10 }}>
                    <span style={{ width: 28, height: 28, borderRadius: 50, background: '#6366f1', color: '#fff', display: 'inline-flex', alignItems: 'center', justifyContent: 'center', fontSize: 11, fontWeight: 700 }}>{l.name.split(' ').map(n => n[0]).join('')}</span>
                    <span>{l.name}</span>
                  </div>
                </td>
                <td style={{ padding: '14px 16px' }}>{l.company}</td>
                <td style={{ padding: '14px 16px' }}>
                  <span style={{ color: getStageColor(l.stage), fontWeight: 600 }}>● {l.stage}</span>
                </td>
                <td style={{ padding: '14px 16px', fontWeight: 600 }}>${l.value.toLocaleString()}</td>
                <td style={{ padding: '14px 16px' }}>
                  <span style={{ color: getStatusColor(l.status), fontWeight: 600, fontSize: 13 }}>{l.status}</span>
                </td>
                <td style={{ padding: '14px 16px' }}>{l.lastContact}</td>
                <td style={{ padding: '14px 16px' }}>
                  <button style={{ background: 'none', border: 'none', color: '#818cf8', cursor: 'pointer', fontWeight: 600 }}>...</button>
                </td>
              </tr>
            ))}
          </tbody>
        </table>
      </div>
    </div>
  );

  const renderConversations = () => (
    <div style={{ display: 'flex', flexDirection: 'column', gap: 16 }}>
      <div style={{ display: 'flex', justifyContent: 'space-between', alignItems: 'center' }}>
        <div>
          <div style={{ fontSize: 20, fontWeight: 700 }}>AI Conversations</div>
          <div style={{ fontSize: 14, color: '#9aa6bd' }}>Review and manage your AI's live conversations</div>
        </div>
        <div style={{ display: 'flex', gap: 10 }}>
          <button style={{ padding: '8px 14px', borderRadius: 8, background: '#6366f1', color: '#fff', border: 'none', fontSize: 13, fontWeight: 600, cursor: 'pointer' }}>
            <PlayCircle size={15} style={{ verticalAlign: 'middle', marginRight: 6 }} />Autopilot On
          </button>
        </div>
      </div>
      <div style={{ display: 'grid', gridTemplateColumns: '300px 1fr', gap: 16 }}>
        <div style={{ background: '#141a30', borderRadius: 14, border: '1px solid #232b45', overflow: 'hidden' }}>
          {(conversations || []).map((c, i) => (
            <div key={i} onClick={() => setActiveChat(c.id)} style={{
              padding: '16px', cursor: 'pointer', borderBottom: '1px solid #1a2340',
              background: activeChat === c.id ? '#1e2646' : 'transparent',
              transition: 'background 0.2s ease',
            }}>
              <div style={{ display: 'flex', justifyContent: 'space-between', alignItems: 'center' }}>
                <div style={{ display: 'flex', alignItems: 'center', gap: 10 }}>
                  <div style={{ width: 32, height: 32, borderRadius: 50, background: '#6366f1', color: '#fff', display: 'flex', alignItems: 'center', justifyContent: 'center', fontWeight: 700, fontSize: 12 }}>{c.lead.split(' ').map(n => n[0]).join('')}</div>
                  <div>
                    <div style={{ fontSize: 14, fontWeight: 600 }}>{c.lead}</div>
                    <div style={{ fontSize: 12, color: '#9aa6bd' }}>{c.channel} · {c.time}</div>
                  </div>
                </div>
                {c.unread && <span style={{ width: 8, height: 8, borderRadius: 50, background: '#6366f1' }} />}
              </div>
              <div style={{ fontSize: 12, color: '#9aa6bd', marginTop: 8, lineHeight: 1.4 }}>{c.preview}</div>
            </div>
          ))}
          {!conversations.length && <div style={{ padding: 20, fontSize: 13, color: '#9aa6bd', textAlign: 'center' }}>No conversations yet. Your AI will start reaching out.</div>}
        </div>
        <div style={{ background: '#141a30', borderRadius: 14, border: '1px solid #232b45', display: 'flex', flexDirection: 'column', height: '100%', minHeight: 420 }}>
          <div style={{ padding: 16, borderBottom: '1px solid #1a2340', display: 'flex', justifyContent: 'space-between', alignItems: 'center' }}>
            <div>
              <div style={{ fontSize: 15, fontWeight: 700 }}>{conversations.find(c => c.id === activeChat)?.lead || 'Chat'}</div>
              <div style={{ fontSize: 12, color: '#34d399' }}>● AI Assistant active</div>
            </div>
            <div style={{ display: 'flex', gap: 8 }}>
              <button style={{ background: 'none', border: '1px solid #232b45', borderRadius: 8, padding: '6px 12px', color: '#9aa6bd', fontSize: 12, cursor: 'pointer' }}>Take Over</button>
              <button style={{ background: 'none', border: '1px solid #ef4444', borderRadius: 8, padding: '6px 12px', color: '#ef4444', fontSize: 12, cursor: 'pointer' }}>End</button>
            </div>
          </div>
          <div style={{ flex: 1, padding: 16, display: 'flex', flexDirection: 'column', gap: 12, overflow: 'auto' }}>
            {(messages || []).map((m, i) => (
              <div key={i} style={{ display: 'flex', justifyContent: m.role === 'user' ? 'flex-end' : 'flex-start' }}>
                <div style={{
                  maxWidth: '70%', padding: '10px 14px', borderRadius: 12,
                  background: m.role === 'user' ? '#6366f1' : '#1e2646',
                  fontSize: 14, lineHeight: 1.5,
                  borderBottomRightRadius: m.role === 'user' ? 4 : 12,
                  borderBottomLeftRadius: m.role === 'ai' ? 4 : 12,
                }}>{m.text}</div>
              </div>
            ))}
          </div>
          <div style={{ padding: 16, borderTop: '1px solid #1a2340', display: 'flex', gap: 10 }}>
            <input value={messageInput} onChange={(e) => setMessageInput(e.target.value)} onKeyDown={(e) => e.key === 'Enter' && sendMessage()} placeholder="Type a message or instruct your AI assistant..." style={{ flex: 1, padding: '10px 14px', borderRadius: 10, border: '1px solid #232b45', background: '#0b1020', color: '#e6eaf2', fontSize: 14, outline: 'none' }} />
            <button onClick={sendMessage} style={{ padding: '10px 18px', borderRadius: 10, background: '#6366f1', color: '#fff', border: 'none', fontWeight: 600, cursor: 'pointer' }}>
              Send
            </button>
          </div>
        </div>
      </div>
    </div>
  );

  const renderAutomations = () => (
    <div style={{ display: 'flex', flexDirection: 'column', gap: 16 }}>
      <div style={{ display: 'flex', justifyContent: 'space-between', alignItems: 'center' }}>
        <div>
          <div style={{ fontSize: 20, fontWeight: 700 }}>Automations</div>
          <div style={{ fontSize: 14, color: '#9aa6bd' }}>Your autonomous workflows running 24/7</div>
        </div>
        <button style={{ padding: '10px 18px', borderRadius: 10, background: '#6366f1', color: '#fff', border: 'none', fontWeight: 600, fontSize: 14, cursor: 'pointer' }}>+ New Automation</button>
      </div>
      <div style={{ display: 'grid', gridTemplateColumns: 'repeat(auto-fill, minmax(340px, 1fr))', gap: 16 }}>
        {(automations || []).map((a, i) => (
          <div key={i} style={{ background: '#141a30', borderRadius: 14, padding: 20, border: '1px solid #232b45' }}>
            <div style={{ display: 'flex', justifyContent: 'space-between', alignItems: 'flex-start', marginBottom: 16 }}>
              <div style={{ display: 'flex', alignItems: 'center', gap: 10 }}>
                <div style={{ width: 36, height: 36, borderRadius: 10, background: a.status === 'Active' ? 'rgba(52,211,153,0.1)' : 'rgba(148,163,184,0.1)', display: 'flex', alignItems: 'center', justifyContent: 'center' }}>
                  <Zap size={18} color={a.status === 'Active' ? '#34d399' : '#9aa6bd'} />
                </div>
                <div>
                  <div style={{ fontSize: 15, fontWeight: 700 }}>{a.name}</div>
                  <div style={{ fontSize: 12, color: a.status === 'Active' ? '#34d399' : '#9aa6bd', fontWeight: 600 }}>● {a.status}</div>
                </div>
              </div>
              <span style={{ fontSize: 12, color: '#9aa6bd' }}>Next: {a.nextRun}</span>
            </div>
            <div style={{ display: 'grid', gridTemplateColumns: 'repeat(3, 1fr)', gap: 10, marginTop: 12 }}>
              {[{ label: 'Runs', value: a.runs }, { label: 'Success', value: `${a.success}%` }, { label: 'Actions', value: '3 steps' }].map((s, j) => (
                <div key={j} style={{ background: '#0f1424', padding: '10px', borderRadius: 8, textAlign: 'center' }}>
                  <div style={{ fontSize: 16, fontWeight: 700 }}>{s.value}</div>
                  <div style={{ fontSize: 11, color: '#9aa6bd' }}>{s.label}</div>
                </div>
              ))}
            </div>
            <div style={{ display: 'flex', gap: 10, marginTop: 16 }}>
              <button style={{ flex: 1, padding: '8px', borderRadius: 8, background: 'transparent', border: `1px solid ${a.status === 'Active' ? '#ef4444' : '#34d399'}`, color: a.status === 'Active' ? '#ef4444' : '#34d399', fontSize: 12, fontWeight: 600, cursor: 'pointer' }}>
                {a.status === 'Active' ? 'Pause' : 'Activate'}
              </button>
              <button style={{ flex: 1, padding: '8px', borderRadius: 8, background: 'transparent', border: '1px solid #232b45', color: '#e6eaf2', fontSize: 12, fontWeight: 600, cursor: 'pointer' }}>Edit</button>
            </div>
          </div>
        ))}
      </div>
    </div>
  );

  const renderCampaigns = () => (
    <div style={{ display: 'flex', flexDirection: 'column', gap: 16 }}>
      <div style={{ display: 'flex', justifyContent: 'space-between', alignItems: 'center' }}>
        <div>
          <div style={{ fontSize: 20, fontWeight: 700 }}>Campaigns</div>
          <div style={{ fontSize: 14, color: '#9aa6bd' }}>Track outreach performance across channels</div>
        </div>
        <button style={{ padding: '10px 18px', borderRadius: 10, background: '#6366f1', color: '#fff', border: 'none', fontWeight: 600, fontSize: 14, cursor: 'pointer' }}>+ Create Campaign</button>
      </div>
      <div style={{ background: '#141a30', borderRadius: 14, border: '1px solid #232b45', overflow: 'hidden' }}>
        <table style={{ width: '100%', borderCollapse: 'collapse', fontSize: 14 }}>
          <thead>
            <tr style={{ background: '#0f1424' }}>
              {['Campaign', 'Leads', 'Replies', 'Meetings', 'Reply Rate', 'Status', ''].map((h, i) => (
                <th key={i} style={{ padding: '14px 16px', textAlign: 'left', fontSize: 12, fontWeight: 700, color: '#9aa6bd', textTransform: 'uppercase', letterSpacing: 0.5, borderBottom: '1px solid #232b45' }}>{h}</th>
              ))}
            </tr>
          </thead>
          <tbody>
            {(campaigns || []).map((c, i) => (
              <tr key={i} style={{ borderBottom: i < campaigns.length - 1 ? '1px solid #1a2340' : 'none' }}>
                <td style={{ padding: '14px 16px', fontWeight: 600 }}>{c.name}</td>
                <td style={{ padding: '14px 16px' }}>{c.leads.toLocaleString()}</td>
                <td style={{ padding: '14px 16px', color: '#34d399', fontWeight: 600 }}>{c.replied}</td>
                <td style={{ padding: '14px 16px', color: '#818cf8', fontWeight: 600 }}>{c.meetings}</td>
                <td style={{ padding: '14px 16px' }}>{((c.replied / c.leads) * 100).toFixed(1)}%</td>
                <td style={{ padding: '14px 16px' }}>
                  <span style={{ color: c.status === 'Live' ? '#34d399' : '#9aa6bd', fontSize: 12, fontWeight: 600 }}>● {c.status}</span>
                </td>
                <td style={{ padding: '14px 16px' }}>
                  <button style={{ background: 'none', border: 'none', color: '#818cf8', cursor: 'pointer', fontWeight: 600 }}>...</button>
                </td>
              </tr>
            ))}
          </tbody>
        </table>
      </div>
    </div>
  );

  const renderContent = () => {
    switch (view) {
      case 'leads': return renderLeads();
      case 'conversations': return renderConversations();
      case 'automations': return renderAutomations();
      case 'campaigns': return renderCampaigns();
      default: return renderOverview();
    }
  };

  return (
    <div style={{ minHeight: '100vh', background: '#0a0d18', color: '#e6eaf2', display: 'flex' }}>
      {/* Sidebar */}
      {sidebarOpen && (
        <div onClick={() => setSidebarOpen(false)} style={{ position: 'fixed', inset: 0, background: 'rgba(2,6,18,.6)', zIndex: 45, '@media (min-width: 769px)': { display: 'none' } }} />
      )}
      <aside style={{
        width: 240, background: '#0f1424', borderRight: '1px solid #232b45', flexShrink: 0, display: 'flex', flexDirection: 'column',
        position: 'fixed', top: 0, bottom: 0, left: 0, zIndex: 50,
        transform: sidebarOpen ? 'translateX(0)' : 'translateX(-100%)',
        transition: 'transform 0.25s ease',
        '@media (min-width: 769px)': { transform: 'translateX(0)', position: 'sticky', top: 0, height: '100vh' },
      }}>
        <div style={{ padding: '24px 20px', display: 'flex', alignItems: 'center', gap: 10, borderBottom: '1px solid #1a2340' }}>
          <div style={{ width: 36, height: 36, borderRadius: 10, background: 'linear-gradient(145deg, #00A8E8, #0077B6)', display: 'flex', alignItems: 'center', justifyContent: 'center' }}>
            <Zap size={18} color="#FFFFFF" />
          </div>
          <div>
            <div style={{ fontSize: 18, fontWeight: 800 }}>SocialQ</div>
            <div style={{ fontSize: 11, color: '#9aa6bd' }}>AI Growth Agent</div>
          </div>
          <button onClick={() => setSidebarOpen(false)} style={{ marginLeft: 'auto', background: 'none', border: 'none', color: '#9aa6bd', cursor: 'pointer', fontSize: 18, '@media (min-width: 769px)': { display: 'none' } }}>✕</button>
        </div>
        <nav style={{ flex: 1, padding: '20px 12px', display: 'flex', flexDirection: 'column', gap: 4 }}>
          {(navItems || []).map((item, i) => (
            <button key={i} onClick={() => setView(item.id)} style={{
              display: 'flex', alignItems: 'center', gap: 10, padding: '10px 12px', borderRadius: 10,
              background: view === item.id ? '#252e52' : 'transparent', border: 'none', color: view === item.id ? '#fff' : '#9aa6bd',
              fontSize: 14, fontWeight: 600, cursor: 'pointer', textAlign: 'left', width: '100%',
              transition: 'background 0.2s ease, color 0.2s ease',
            }}>
              {item.icon}
              <span style={{ flex: 1 }}>{item.label}</span>
              {item.badge && <span style={{ background: '#6366f1', color: '#fff', borderRadius: 20, fontSize: 11, fontWeight: 700, padding: '2px 8px' }}>{item.badge}</span>}
            </button>
          ))}
        </nav>
        <div style={{ padding: '16px 12px', borderTop: '1px solid #1a2340' }}>
          <div style={{ background: '#141a30', borderRadius: 12, padding: 14, border: '1px solid #232b45' }}>
            <div style={{ display: 'flex', alignItems: 'center', gap: 8, marginBottom: 10 }}>
              <div style={{ width: 28, height: 28, borderRadius: 50, background: '#6366f1', color: '#fff', display: 'flex', alignItems: 'center', justifyContent: 'center', fontSize: 12, fontWeight: 700 }}>
                {(user?.name || user?.email || 'U')[0].toUpperCase()}
              </div>
              <div style={{ flex: 1, fontSize: 13, fontWeight: 600, overflow: 'hidden', textOverflow: 'ellipsis', whiteSpace: 'nowrap' }}>
                {user?.name || user?.email}
              </div>
              <button onClick={() => setShowProfileMenu(!showProfileMenu)} style={{ background: 'none', border: 'none', color: '#9aa6bd', cursor: 'pointer', fontSize: 14 }}>⋯</button>
            </div>
            {showProfileMenu && (
              <div style={{ background: '#0f1424', borderRadius: 8, overflow: 'hidden', marginTop: 4 }}>
                <button onClick={onLogout} style={{ display: 'block', width: '100%', padding: '8px 12px', background: 'transparent', border: 'none', color: '#ef4444', fontSize: 13, fontWeight: 600, cursor: 'pointer', textAlign: 'left' }}>Log out</button>
              </div>
            )}
          </div>
        </div>
      </aside>

      {/* Main content */}
      <main style={{ flex: 1, marginLeft: 0, '@media (min-width: 769px)': { marginLeft: 240 }, minWidth: 0, display: 'flex', flexDirection: 'column' }}>
        {/* Top bar */}
        <div style={{ position: 'fixed', top: 0, left: 0, right: 0, background: '#0a0d18', borderBottom: '1px solid #1a2340', padding: '14px 24px', display: 'flex', alignItems: 'center', justifyContent: 'space-between', zIndex: 40, '@media (min-width: 769px)': { left: 240 } }}>
          <div style={{ display: 'flex', alignItems: 'center', gap: 12 }}>
            <button onClick={() => setSidebarOpen(true)} style={{ background: 'none', border: 'none', color: '#9aa6bd', cursor: 'pointer', display: 'flex', '@media (min-width: 769px)': { display: 'none' } }}>
              <Menu size={22} />
            </button>
            <div>
              <div style={{ fontSize: 16, fontWeight: 700 }}>{navItems.find(n => n.id === view)?.label || 'Overview'}</div>
              <div style={{ fontSize: 12, color: '#9aa6bd' }}>Autopilot running · {new Date().toLocaleTimeString([], { hour: '2-digit', minute: '2-digit' })}</div>
            </div>
          </div>
          <div style={{ display: 'flex', gap: 8, alignItems: 'center' }}>
            <div style={{ display: 'flex', alignItems: 'center', gap: 8, background: 'rgba(52,211,153,0.1)', padding: '8px 14px', borderRadius: 20 }}>
              <span style={{ width: 8, height: 8, borderRadius: 50, background: '#34d399' }} className="animate-pulse-slow"></span>
              <span style={{ fontSize: 12, color: '#34d399', fontWeight: 700 }}>Autopilot Active</span>
            </div>
            <button style={{ background: '#6366f1', border: 'none', padding: '8px 16px', borderRadius: 10, color: '#fff', fontWeight: 600, fontSize: 13, cursor: 'pointer' }}>+ New Lead</button>
          </div>
        </div>

        {/* Content area */}
        <div style={{ padding: '88px 24px 32px', flex: 1, minWidth: 0 }}>
          {renderContent()}
        </div>
      </main>
    </div>
  );
}

function AuthGate({ onAuth, onClose }) {
  const [mode, setMode] = useState('signup');
  const [form, setForm] = useState({ name: '', email: '', password: '' });
  const [loading, setLoading] = useState(false);
  const [error, setError] = useState('');
  const _ip = { width: '100%', padding: '11px 13px', margin: '6px 0', borderRadius: 9, border: '1px solid #2a3350', background: '#0b1020', color: '#e6eaf2', fontSize: 14, outline: 'none', boxSizing: 'border-box' };
  const submit = async (e) => {
    e.preventDefault();
    if (!form.email || !form.password) return;
    setLoading(true); setError('');
    const _b = window.__NC_BASE__ || ''; const _s = window.__COMPANY_SLUG__ || '';
    const body = JSON.stringify({ email: form.email, password: form.password, name: form.name });
    const _call = () => fetch(`${_b}/api/c/${_s}/auth/${mode}`, { method: 'POST', headers: { 'Content-Type': 'application/json' }, body });
    try {
      let res; try { res = await _call(); } catch { await new Promise(r => setTimeout(r, 2500)); res = await _call(); }
      const json = await res.json();
      if (!json.ok) { setError(json.error || 'Authentication failed — please try again'); setLoading(false); return; }
      onAuth(json);
    } catch { setError('Connection error — please try again in a moment.'); setLoading(false); }
  };
  return (
    <div onClick={onClose} style={{ position: 'fixed', inset: 0, background: 'rgba(2,6,18,.7)', backdropFilter: 'blur(4px)', display: 'flex', alignItems: 'center', justifyContent: 'center', zIndex: 1000 }}>
      <form onClick={(e) => e.stopPropagation()} onSubmit={submit} style={{ background: '#0f1424', border: '1px solid #232b45', padding: 28, borderRadius: 16, width: 360, maxWidth: '90vw', color: '#e6eaf2' }}>
        <h3 style={{ margin: '0 0 16px', fontSize: 20, fontWeight: 700 }}>{mode === 'signup' ? 'Create your account' : 'Welcome back'}</h3>
        {mode === 'signup' && <input value={form.name} onChange={(e) => setForm({ ...form, name: e.target.value })} placeholder="Your name" style={_ip} />}
        <input value={form.email} onChange={(e) => setForm({ ...form, email: e.target.value })} placeholder="Work email" type="email" required style={_ip} />
        <input value={form.password} onChange={(e) => setForm({ ...form, password: e.target.value })} placeholder="Password (min 6 chars)" type="password" required style={_ip} />
        {error && <p style={{ color: '#f87171', fontSize: 13, margin: '6px 0 0' }}>{error}</p>}
        <button type="submit" disabled={loading} style={{ width: '100%', marginTop: 10, padding: '12px', borderRadius: 9, border: 'none', background: loading ? '#4b50b8' : '#6366f1', color: '#fff', fontWeight: 700, fontSize: 15, cursor: loading ? 'default' : 'pointer' }}>
          {loading ? '…' : mode === 'signup' ? 'Get started free' : 'Log in'}
        </button>
        <p onClick={() => { setMode(mode === 'signup' ? 'login' : 'signup'); setError(''); }} style={{ marginTop: 14, fontSize: 13, color: '#9aa6bd', cursor: 'pointer', textAlign: 'center' }}>
          {mode === 'signup' ? 'Already have an account? Log in' : 'New here? Create an account'}
        </p>
      </form>
    </div>
  );
}

function App() {
  const [auth, setAuth] = useState(() => {
    try {
      if (localStorage.getItem('nc_user') && !localStorage.getItem('nc_auth')) localStorage.removeItem('nc_user');
      const a = JSON.parse(localStorage.getItem('nc_auth') || 'null');
      return (a && a.token && a.user && typeof a.user.email === 'string') ? a : null;
    } catch { return null; }
  });
  const [showAuth, setShowAuth] = useState(false);
  useEffect(() => {
    if (!auth?.token) return;
    const _b = window.__NC_BASE__ || ''; const _s = window.__COMPANY_SLUG__ || '';
    fetch(`${_b}/api/c/${_s}/auth/me`, { headers: { Authorization: `Bearer ${auth.token}` } })
      .then(r => r.json()).then(d => { if (!d.ok) { localStorage.removeItem('nc_auth'); setAuth(null); } }).catch(() => {});
  }, []);
  const onAuth = (data) => { localStorage.setItem('nc_auth', JSON.stringify(data)); setAuth(data); setShowAuth(false); };
  const onLogout = () => { localStorage.removeItem('nc_auth'); setAuth(null); };
  if (auth?.user) return <ProductApp user={auth.user} token={auth.token} onLogout={onLogout} />;
  return (
    <>
      <LandingPage onGetStarted={() => setShowAuth(true)} onSignup={() => setShowAuth(true)} onLogin={() => setShowAuth(true)} />
      {/* Fallback entry point (bottom-right so it never overlaps the nav) — guarantees a
          working login even if the landing's own buttons aren't wired to the auth modal. */}
      <button onClick={() => setShowAuth(true)} style={{ position: 'fixed', bottom: 20, right: 20, zIndex: 999, background: '#6366f1', color: '#fff', border: 'none', padding: '10px 18px', borderRadius: 999, fontWeight: 600, fontSize: 14, cursor: 'pointer', boxShadow: '0 6px 20px rgba(99,102,241,.45)' }}>Sign in</button>
      {showAuth && <AuthGate onAuth={onAuth} onClose={() => setShowAuth(false)} />}
    </>
  );
}

export default App;
// pages/brands/[brand].tsx
import { useRouter } from "next/router";
import Head from "next/head";
import Link from "next/link";

const brandData: Record<string, { title: string; description: string; specs: string[]; note?: string }> = {
  "shree-flyash-aac": {
    title: "Shree Flyash AAC",
    description:
      "Fly-ash based AAC blocks with consistent quality and thermal insulation — suitable for residential & commercial projects.",
    specs: ["Sizes: 625×200×100/125/150/200/230 mm", "Density: 550–650 kg/m³", "Compressive Strength: 3–5 N/mm²"],
  },
  "finecrete": {
    title: "Finecrete",
    description: "High-strength AAC blocks optimized for speed of masonry and uniform finish.",
    specs: ["Precision-cut sizes", "Low water absorption", "Good dimensional stability"],
  },
  "magicrete": {
    title: "Magicrete",
    description:
      "Magicrete AAC Blocks are known for superior strength, lightweight and eco-friendliness. Widely used across India for faster construction.",
    specs: ["Size matrix available", "Thermal & acoustic benefits", "Consistent density control"],
  },
  "dlite": {
    title: "Dlite",
    description: "Lightweight AAC solutions targeted at residential developers and builders.",
    specs: ["Low unit weight", "Easy handling", "Fast dry times"],
  },
  "birla-nuvo-walls": {
    title: "Birla NuVo (Walls)",
    description: "Birla Group backed AAC wall solutions with strong distribution and quality assurance.",
    specs: ["Industrial-scale production", "Brand reliability", "Good warranty support"],
  },
  "renacon": {
    title: "Renacon",
    description: "Cost-effective AAC block solutions for medium to large-scale construction projects.",
    specs: ["Competitive pricing", "ISI/quality checks", "Good for bulk orders"],
  },
  "greenstone": {
    title: "Greenstone",
    description: "Eco-friendly AAC blocks with reduced embodied energy and good thermal performance.",
    specs: ["Sustainable sourcing", "Thermal insulation", "Low clinker content"],
  },
  "magna-green": {
    title: "Magna Green",
    description: "High-performance AAC with emphasis on thermal & acoustic ratings for premium projects.",
    specs: ["High acoustic attenuation", "Stable compressive strength", "Uniform cells"],
  },
  "biltech": {
    title: "Biltech",
    description: "Manufactured AAC blocks with a wide distribution network suitable for pan-India supply.",
    specs: ["Multiple plants", "Stable supply chain", "Well-documented specs"],
  },
  "conecc-concrete": {
    title: "Conecc Concrete",
    description: "Industrial-grade AAC blocks supplier with options for modular and structural uses.",
    specs: ["Industrial capacities", "Bulk delivery", "Site logistics support"],
  },
  "ecolite": {
    title: "Ecolite",
    description: "Energy-efficient AAC blocks optimized for insulation and saving HVAC costs over lifecycle.",
    specs: ["Low thermal conductivity", "Fire-resistant", "Durable"],
  },
  "infra-market": {
    title: "Infra.Market (AAC vendors)",
    description: "Marketplace-sourced AAC with verified vendors and logistics integration.",
    specs: ["Vendor-verification", "Multiple brand options", "Integrated logistics"],
  },
  "aercon-india": {
    title: "Aercon India",
    description: "Aerated concrete leaders using global tech for high-quality AAC products.",
    specs: ["Proven tech", "High uniformity", "Tall building suitability"],
  },
  "meghalite": {
    title: "Meghalite",
    description: "Regional AAC brand with consistent quality and cost-effective variants.",
    specs: ["Regional distribution", "Competitive pricing", "Quality control"],
  },
  "jk-lakshmi-aac": {
    title: "JK Lakshmi (Fly Ash AAC)",
    description: "Cement-house backed AAC with strong raw-material control and brand trust.",
    specs: ["Cement-house reliability", "Consistent mix design", "Large order handling"],
  },
  "fusion": {
    title: "Fusion",
    description: "Modular AAC systems and engineered blocks for quick on-site assembly and speed-of-build.",
    specs: ["Modular systems", "Uniform tolerances", "Developer-focused"],
  },
  "brikolite": {
    title: "Brikolite",
    description: "Economical AAC block options targeting cost-sensitive builders and projects.",
    specs: ["Economical grades", "Good availability", "Bulk-friendly"],
  },
  "go-green-aac": {
    title: "Go Green AAC",
    description: "Sustainable, green-branded AAC blocks emphasizing lower CO₂ footprint.",
    specs: ["Sustainable mix", "Lifecycle benefits", "Green certifications (where available)"],
  },
  "ashtech-india": {
    title: "Ashtech India",
    description: "Performance-oriented AAC with specialized mixes for targeted applications.",
    specs: ["Tailored mixes", "High-performance grades", "Technical support available"],
  },
  "clavecon": {
    title: "Clavecon",
    description: "Precision-manufactured AAC blocks for modular builds and tighter tolerances.",
    specs: ["Precision tolerances", "Good for prefabrication", "Structural consistency"],
  },
};

export default function BrandPage() {
  const router = useRouter();
  const { brand } = router.query;
  const data = brand ? brandData[brand.toString().toLowerCase()] : null;

  if (!brand || !data) return <p className="p-6">Brand details not found. Please select a valid brand.</p>;

  return (
    <main className="min-h-screen bg-white text-gray-900">
      <Head>
        <title>{data.title} AAC Blocks | Rodi Dust — Dealer & Distributor</title>
        <meta name="description" content={`${data.title} AAC blocks: ${data.description}. Contact RODI DUST for bulk rates & delivery across Delhi NCR & India.`} />
      </Head>

      <section className="px-6 py-12 max-w-5xl mx-auto">
        <h1 className="text-3xl font-bold mb-4">{data.title} — AAC Blocks</h1>
        <p className="mb-6 text-slate-700">{data.description}</p>

        <h2 className="text-xl font-semibold mb-3">Key Specifications</h2>
        <ul className="list-disc ml-6 mb-6">
          {data.specs.map((spec, idx) => (
            <li key={idx}>{spec}</li>
          ))}
        </ul>

        {data.note && <div className="mb-6 text-sm text-amber-700">Note: {data.note}</div>}

        <div className="grid grid-cols-1 md:grid-cols-2 gap-6">
          <div className="p-4 border rounded">
            <h3 className="font-semibold mb-2">Typical Sizes</h3>
            <ul className="list-disc ml-6">
              <li>625 × 200 × 100 mm</li>
              <li>625 × 200 × 125 mm</li>
              <li>625 × 200 × 150 mm</li>
              <li>625 × 200 × 200 mm</li>
              <li>Other custom sizes on request</li>
            </ul>
          </div>

          <div className="p-4 border rounded">
            <h3 className="font-semibold mb-2">Technical Snapshot</h3>
            <table className="w-full text-sm">
              <tbody>
                <tr><td>Density</td><td className="text-right">~550–650 kg/m³</td></tr>
                <tr><td>Compressive Strength</td><td className="text-right">~3–5 N/mm²</td></tr>
                <tr><td>Thermal Conductivity</td><td className="text-right">~0.16–0.24 W/mK</td></tr>
                <tr><td>Fire Rating</td><td className="text-right">≥ 4 hours (typical)</td></tr>
              </tbody>
            </table>
          </div>
        </div>

        <div className="mt-8 flex gap-3">
          <a href="tel:+919582872872" className="px-4 py-2 bg-blue-600 text-white rounded">Call: 9582-872-872</a>
          <a href={`https://wa.me/919582872872?text=I%20want%20a%20quote%20for%20${encodeURIComponent(data.title)}`} target="_blank" rel="noreferrer" className="px-4 py-2 bg-green-600 text-white rounded">WhatsApp for Quote</a>
          <Link href="/contact" className="px-4 py-2 border rounded">Contact Page</Link>
        </div>
      </section>
    </main>
  );
}

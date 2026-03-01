# Changelog

All notable changes to NutriGx Advisor are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

## [0.2.0-openclaw] — 2026-02-28

### Added

#### OpenClaw Adaptation
- **`openclaw_adapter.py`** — Function-based entry point for OpenClaw platform
  - `NutriGxOpenClaw` class wraps core analysis
  - `run_analysis()` entry point for OpenClaw integration
  - Structured JSON output with status, summary, risk scores, and file paths
  - Comprehensive error handling with user-friendly messages
  
- **`openclaw.json`** — Skill manifest for OpenClaw platform
  - Entry point registration
  - Input/output schema definitions
  - Dependency specifications
  - Metadata for platform discovery

#### Documentation
- **`SKILL_OPENCLAW.md`** — User-facing documentation optimised for OpenClaw
  - "How to get your genetic data" guide
  - Quick start workflow
  - Detailed gene descriptions with examples
  - Privacy & security emphasis
  - Comprehensive FAQ and troubleshooting
  
- **`README_OPENCLAW.md`** — Comprehensive user guide for OpenClaw platform
  - Step-by-step tutorial
  - Input file format specifications with examples
  - Understanding results section
  - Support and contribution information
  
- **`IMPLEMENTATION.md`** — Technical deployment guide
  - Installation and testing procedures
  - OpenClaw platform integration steps
  - Environment configuration
  - Performance benchmarks
  - Security verification checklist
  - Troubleshooting for deployment issues

- **`MIGRATION.md`** — Detailed migration guide from ClawBio to OpenClaw
  - Architecture changes explained
  - Behavioral differences documented
  - Scientific integrity verification
  - Backward compatibility notes
  - FAQ for developers

- **`ATTRIBUTION.md`** — Comprehensive attribution and acknowledgments
  - Author and maintainer information
  - Scientific literature citations (15+ peer-reviewed papers)
  - Software and library acknowledgments
  - Citation formats (BibTeX, APA, Chicago)
  - Non-human AI contribution disclosure
  - Ethical considerations and disclaimers

- **`CONTRIBUTORS.md`** — Contributor recognition and guidelines
  - Contribution opportunities listed
  - Recognition levels defined
  - Code of conduct
  - Contributor license agreement template
  - Getting started guide for contributors

- **`CHANGELOG.md`** (this file) — Version history documentation

#### Infrastructure
- **`requirements.txt`** — Python dependency specifications
  - Pinned versions for reproducibility
  - Compatible with Python 3.11+

- **`LICENSE`** — MIT License
  - Full legal text
  - Copyright notice (© 2026 David de Lorenzo)

### Changed

#### Documentation
- **`SKILL.md`** — Retained as original ClawBio documentation
  - No changes to original content
  - Serves as reference for core science
  - Available alongside new OpenClaw materials

### Technical Improvements

- **Error Handling**
  - File format validation with helpful error messages
  - Missing SNP panel detection with clear instructions
  - Panel coverage reporting (percentage of SNPs found)
  - User-friendly error messages (no stack traces)

- **Output Formatting**
  - Structured JSON output for programmatic use
  - Executive summary generation
  - Risk score serialisation
  - Figure path references in result dictionary

- **Documentation Structure**
  - Separated platform-specific guidance
  - Multiple documentation entry points for different audiences
  - Comprehensive cross-referencing
  - Clear attribution and licensing

### Backward Compatibility

✅ **100% backward compatible with ClawBio version**
- All original Python modules unchanged
- SNP panel identical
- Risk scoring algorithm identical
- Report generation identical
- Test suite unchanged

### Documentation Quality

- ✅ 3 comprehensive user guides (SKILL_OPENCLAW, README_OPENCLAW, IMPLEMENTATION)
- ✅ Architecture documentation (MIGRATION)
- ✅ Attribution and licensing (ATTRIBUTION)
- ✅ Contributor guidelines (CONTRIBUTORS)
- ✅ Version history (CHANGELOG)
- ✅ MIT License included

---

## [0.1.0] — 2025-02-27

### Initial Release (ClawBio)

#### Core Features
- **Genetic Data Parsing**
  - 23andMe format support (.txt, .csv)
  - AncestryDNA format support (.csv)
  - VCF format support
  - Automatic format detection

- **SNP Analysis**
  - 58 SNP panel covering 40+ genes
  - Risk scoring (0-10 scale per nutrient)
  - 8 nutrient categories
  - Weighted effect size integration

- **Risk Scoring Categories**
  - Micronutrient metabolism (MTHFR, VDR, BCMO1, etc.)
  - Macronutrient metabolism (APOE, FTO, PPARG, etc.)
  - Omega-3 & PUFA metabolism (FADS1/2, ELOVL2)
  - Caffeine metabolism (CYP1A2, AHR)
  - Alcohol metabolism (ADH1B, ALDH2)
  - Food sensitivities (MCM6, HLA proxies)
  - Antioxidant pathways (SOD2, GPX1, GSTT1, NQO1, COMT)
  - Gene-nutrient interactions

- **Report Generation**
  - Markdown report with gene-by-gene breakdown
  - Radar chart (nutrient risk profile)
  - Heatmap (gene-nutrient interactions)
  - Personalised recommendations
  - Supplement interaction guidance

- **Reproducibility**
  - commands.sh — Full CLI reproducibility
  - environment.yml — Conda environment export
  - checksums.txt — SHA-256 validation
  - provenance.json — Metadata tracking

- **Privacy & Security**
  - Local processing only
  - No data transmission
  - No account required
  - Raw genotypes never exposed in output

#### Scientific Foundation
- Peer-reviewed SNP selection
- GWAS Catalog sourced variants
- ClinVar integrated annotations
- Effect sizes from published literature
- Population frequency data

#### Documentation
- **SKILL.md** — Comprehensive skill documentation for ClawBio
- **SNP panel documentation** with gene descriptions
- **Algorithm explanation** with scoring methodology
- **Usage examples** and CLI instructions

#### Testing
- Unit test suite (pytest)
- Synthetic patient generation for testing
- Example outputs with pre-rendered report
- Edge case validation

---

## Planned Features (Roadmap)

### v0.3.0 (Microbiome Integration)
- [ ] 16S rRNA microbiome input support
- [ ] Microbiome × genotype interaction analysis
- [ ] Personalised probiotic recommendations
- [ ] Microbiome-optimised dietary guidance

### v0.4.0 (Longitudinal Tracking)
- [ ] Multi-report comparison
- [ ] Temporal trend analysis
- [ ] Dietary change impact assessment
- [ ] Report history visualisation

### v0.5.0 (Advanced Immune Analysis)
- [ ] HLA typing from genetic data
- [ ] Coeliac risk assessment
- [ ] Gluten sensitivity prediction
- [ ] Immune-mediated food reaction guidance

### v1.0.0 (Multi-Omics Integration)
- [ ] Metabolomics data integration
- [ ] Gene × metabolite interactions
- [ ] Dietary intake data incorporation
- [ ] Comprehensive phenotype prediction
- [ ] Integration with NeoTree for maternal nutrition scoring

### v1.5.0 (Clinical Integration)
- [ ] Healthcare provider report generation
- [ ] Clinical reference ranges
- [ ] Biomarker testing recommendations
- [ ] EHR integration capabilities

---

## Known Issues & Limitations

### Current Limitations (v0.2.0-openclaw)

1. **Common Variants Only**
   - SNP panel limited to MAF > 1%
   - Rare pathogenic variants not detected
   - Requires clinical genetic testing for rare variants

2. **Population Context**
   - Effect sizes predominantly from European GWAS
   - Accuracy may vary across ancestries
   - Population-specific variants not yet included

3. **Gene × Environment Interaction**
   - Algorithm doesn't account for lifestyle factors
   - Genetic risk scores are probabilistic, not diagnostic
   - Environmental inputs (diet, exercise, stress) not included

4. **Single Test Provider Data**
   - Each test only covers subset of SNPs
   - Panel coverage varies by genotyping chip
   - Some variants may be "NOT_TESTED"

5. **File Size Limitations**
   - Tested up to 50 MB files
   - Larger files may timeout on some systems
   - Streaming parser planned for v0.3.0

### Planned Improvements

- [ ] Population-stratified risk scores (v0.3.0)
- [ ] Environmental factor weighting (v1.0.0)
- [ ] Streaming file parser for large files (v0.3.0)
- [ ] Batch processing capability (v1.0.0)
- [ ] Multi-ancestry model training (v1.5.0)

---

## Security & Privacy Notes

### v0.2.0-openclaw
- ✅ All analysis local (no external API calls)
- ✅ No data persistence after analysis
- ✅ No network transmission of genetic data
- ✅ Input sanitisation for file paths
- ✅ No sensitive data in error messages
- ✅ Temporary files cleaned automatically

### Verification
- No external network calls detected
- File system access restricted to uploads and output
- Memory cleared after analysis completion
- Temp files removed on completion or error

---

## Deprecation Notices

### v0.2.0-openclaw
- No deprecations in initial OpenClaw release
- ClawBio CLI still supported (use original SKILL.md)

### Planned Deprecations
- **v1.0.0**: ClawBio CLI will be deprecated (OpenClaw recommended)
- **v1.5.0**: Legacy input format parsing may be simplified

---

## Migration Guide

### From ClawBio v0.1.0 to OpenClaw v0.2.0-openclaw

See `MIGRATION.md` for detailed instructions:
- No code changes needed for existing analysis
- Use new `openclaw_adapter.py` instead of `nutrigx_advisor.py`
- Same results, improved user interface

---

## Contributors

### v0.2.0-openclaw
- David de Lorenzo ([@drdaviddelorenzo](https://github.com/drdaviddelorenzo)) — Project lead, architecture adaptation
- Claude (Anthropic) — AI-assisted documentation and code generation

### v0.1.0
- David de Lorenzo ([@drdaviddelorenzo](https://github.com/drdaviddelorenzo)) — Original development

---

## License

All versions released under the MIT License.

---

## References

Detailed scientific references available in:
- `ATTRIBUTION.md` — Complete citation list
- `SKILL_OPENCLAW.md` — In-text references by topic
- Original papers — DOI links provided throughout

---

*Last updated: February 28, 2026*
*Current stable version: 0.2.0-openclaw*
*Next planned release: 0.3.0 (Q3 2026)*

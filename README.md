# Tabbed Outline Format (TOF)

A plain-text, tab-indented note-taking format. Hierarchy through real tab characters, no markdown, zero formatting overhead.

**Site:** https://tabbedoutlineformat.com
**Spec:** [SPEC.md](./SPEC.md)
**Version:** `0.1.0-alpha`
**Status:** Alpha — pre-beta, breaking changes possible.

---

## What is TOF?

TOF organizes information as a hierarchy using literal tab characters for indentation. Each tab level represents one deeper layer of detail. Designed for cheat sheets, reference notes, and any content where scannability and density matter more than presentation.

```
Check Docker Version:
	docker --version

Basic Docker Commands
	Images
		List Images:
			docker images
		Pull an Image from Docker Hub:
			docker pull <image-name>
```

## Why TOF?

- Plain text, no markup parser required
- Renders identically in any text editor
- Diff-friendly, version-control-friendly
- Optimized for scanning, not reading
- Zero ceremony

## Examples

See [`examples/`](./examples/) for sample TOF files.

## File Extension (planned)

A dedicated `.tof` file extension is planned for a future release. Currently TOF files use `.txt`.

## License

TBD.

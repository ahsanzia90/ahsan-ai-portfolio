PRODUCTION SAFE FIX

Files:
- index.html
- avatar.glb (Brotli-compressed bytes, served transparently as avatar.glb)
- _headers (tells Netlify to decode Brotli in transit and cache the avatar)

IMPORTANT:
Upload all three files to the same Netlify/GitHub publish directory.
Do not decompress avatar.glb before uploading it.

What changed:
1) Avatar model bytes are unchanged after Brotli decompression; only network transfer is compressed.
2) Native speech is made more resilient on iOS Safari with user-gesture priming and a single conservative retry if speech never starts/errors.
3) Existing avatar animation, lip-sync, renderer settings, UI, and knowledge-base code are otherwise left intact.

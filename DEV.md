command: node -e "require('http').createServer((q,s)=>require('fs').readFile('index.html',(e,d)=>{s.writeHead(e?500:200,{'Content-Type':'text/html; charset=utf-8'});s.end(e?String(e):d)})).listen(3000,()=>console.log('http://localhost:3000'))"
port: 3000

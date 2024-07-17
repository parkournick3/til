## Stream Concept

#### English

Streams in NodeJS are a way of processing data through chunks to avoid overloading the server and return a faster response to whoever is consuming the data, also through chunks.

For example, Youtube delivers the video in chunks to the user, so initially the video doesn't load in its entirety, which could overload Youtube's servers, and it doesn't take long for the user to start watching something.

Example of a simple Readable Stream that counts from 1 to 100, sending 1 chunk per second.

```javascript
import { Readable } from “node:stream”;

// process.stdin.pipe(process.stdout);

class OneToHundredStream extends Readable {
  index = 1;

  _read() {
    const i = this.index++;

    setTimeout(() => {
      if (i > 100) {
        this.push(null);
      } else {
        const buffer = Buffer.from(String(i));
        this.push(buffer);
      }
    }, 1000);
  }
}

new OneToHundredStream().pipe(process.stdout);
```

---

#### Português

Streams no NodeJS é uma forma de processar dados atraves de chuncks para evitar sobrecarga no servidor e devolver um resposta mais rapido para quem estiver consumindo os dados, tambem atraves de chunks

Por exemplo, o Youtube entrega o video em chunks para o usuario, por isso inicialmente o video não carrega inteiro oque poderia sobrecarregar os servidores do Youtube e nem demora para o usuario já começar a assistir algo.

Exemplo de uma Stream Readable simples que conta de 1 até 100, enviando 1 chunk por segundo.

```javascript
import { Readable } from "node:stream";

// process.stdin.pipe(process.stdout);

class OneToHundredStream extends Readable {
  index = 1;

  _read() {
    const i = this.index++;

    setTimeout(() => {
      if (i > 100) {
        this.push(null);
      } else {
        const buffer = Buffer.from(String(i));
        this.push(buffer);
      }
    }, 1000);
  }
}

new OneToHundredStream().pipe(process.stdout);
```

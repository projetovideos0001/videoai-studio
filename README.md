# VideoAI Studio

Interface inicial para uma aplicação web de geração de vídeos por IA a partir de prompts.

## Estado atual
A interface contém controles de prompt, formato, duração e estilo. **A geração real ainda não está conectada**; o botão não chama APIs pagas nem cria um arquivo de vídeo.

## Executar localmente
Requer Node.js 20 ou compatível com Vite 6.

```bash
npm install
npm run dev
npm run build
```

## Próximas etapas
1. Conectar o repositório ao Lovable.
2. Escolher um provedor de vídeo com API, comparando preço, duração, formatos e disponibilidade.
3. Implementar backend para iniciar geração e consultar status.
4. Guardar chaves de API apenas como secrets no backend.
5. Armazenar vídeos em bucket privado e gerar links de download seguros.
6. Exibir limites/custos antes de iniciar tarefas pagas.

## Arquitetura recomendada
- Frontend: React + TypeScript + Vite.
- Backend: função serverless, por exemplo Supabase Edge Functions.
- Provedor de vídeo: adaptador no backend.
- Armazenamento: bucket privado com links temporários.

A duração e os formatos reais dependerão do provedor escolhido.
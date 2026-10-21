# VideoAI Studio

Interface inicial para uma aplicação web de geração de vídeos por IA a partir de prompts.

## Estado atual
A tela Criar vídeo permite selecionar até 5 imagens (PNG, JPG/JPEG, WEBP ou GIF) e PDFs de até 10 MB cada. Neste estágio, os anexos ficam apenas na sessão do navegador: **ainda não são enviados para armazenamento nem encaminhados ao provedor de vídeo**. A leitura/extracção de texto de PDFs e a geração real de vídeo pelo app ainda não estão conectadas.

## Executar localmente
Requer Node.js 20 ou compatível com Vite 6.

```bash
npm install
npm run dev
npm run build
```

## Verificação automática
O GitHub Actions executa `npm run build` em pushes para a branch principal e em pull requests destinados a `main`, para detectar erros de TypeScript e compilação antes da integração.

## Próximas etapas
1. Configurar um backend e armazenamento privado para os anexos.
2. Enviar os arquivos para armazenamento com validação no servidor e regras de acesso.
3. Extrair texto dos PDFs no backend, quando necessário, e preparar imagens para o provedor.
4. Conectar o backend ao provedor de geração de vídeo.
5. Guardar vídeos em bucket privado e gerar links de download seguros.
6. Exibir limites/custos antes de iniciar tarefas pagas.

## Arquitetura recomendada
- Frontend: React + TypeScript + Vite.
- Backend: função serverless, por exemplo Supabase Edge Functions.
- Provedor de vídeo: adaptador no backend.
- Armazenamento: bucket privado com links temporários.

A duração e os formatos reais dependerão do provedor escolhido. Não coloque chaves de API no frontend.

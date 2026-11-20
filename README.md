# Esteira IMOB

Assistente de IA para corretores de imóveis: atende o cliente pelo WhatsApp (simulado), qualifica o lead, apresenta os imóveis do corretor, valida os documentos do financiamento em segundos e entrega o dossiê organizado.

Projeto de autoria de Randell, desenvolvido para o Processo Seletivo de Inovação do CITi, novembro de 2026.

## O problema

No financiamento imobiliário, o cliente manda a foto do documento e só descobre dias depois que estava cortada, borrada, vencida ou errada. O corretor gasta o tempo triando leads e cobrando documento, em vez de visitar, negociar e produzir conteúdo para atrair clientes.

## O que o protótipo faz

- Conversa conduzida por IA (sem roteiro fixo): responde dúvidas, aceita perguntas fora do assunto e nunca inventa taxa, prazo ou aprovação.
- Consentimento e transparência desde a primeira mensagem.
- Qualificação do lead (renda, ocupação, estado civil, FGTS, restrição, entrada) com temperatura e resumo para o corretor.
- Lista de documentos sob medida para o perfil do cliente.
- Validação de documentos por imagem: tipo, qualidade, validade e nome.
- Dossiê com arquivos renomeados (`01_RG_JoaoSilva`, `02_Renda_JoaoSilva`...).
- Perfil e catálogo do corretor (nome do agente, imóveis, preços, pontos de referência, fotos). A foto só é enviada se o cliente aceitar.
- Simulação de aprovação e de reprovação, com plano de relacionamento em 30 e 60 dias.

## Como foi feito

- Página única em HTML, CSS e JavaScript puro, sem framework.
- IA: Claude (Anthropic), com entrada de texto e imagem e saída em JSON, por meio do recurso de chamada de IA da plataforma de artefatos do Claude.
- Imagens reduzidas e documentos de teste gerados com Canvas, no navegador.
- Perfil e catálogo guardados no `localStorage` (somente protótipo).
- Desenvolvido em parceria com o Claude: ideação, arquitetura, código e testes. Detalhes na documentação.

## Importante: como executar

O arquivo `esteira-imob.html` chama a IA por um recurso que **só existe dentro do ambiente de artefatos do Claude**. Abrindo o arquivo diretamente no navegador, a página carrega, mas a conversa e a leitura de documentos não funcionam. Para ver o produto rodando:

- assista ao **vídeo da demonstração**:https://youtu.be/AcgGvJJGDoQ?si=Ny67htA9scKHmpQO;
- ou abra o **link publicado** (requer conta no Claude): https://claude.ai/artifact/GQohDQaNKGn4654hFQHbsK

Para rodar fora do Claude, seria necessário um pequeno servidor que chame a API da Anthropic com uma chave protegida. Isso está no roadmap.

## Limitações

- O WhatsApp é simulado. O caminho oficial é a API do WhatsApp Business.
- Os documentos usados na demonstração são **fictícios**. Não use documentos reais.
- A IA pode errar na leitura de imagens reais; o corretor revisa o dossiê e a decisão de crédito nunca é da IA.
- Arquivos do dossiê saem em imagem (JPG), não em PDF.
- Catálogo salvo apenas no navegador, sem contas nem sincronização.
- Áudio ainda não é interpretado.

## Próximos passos

1. Integração oficial com o WhatsApp Business.
2. Contas de corretor, banco de dados seguro, criptografia e exclusão automática.
3. Interpretação de áudios do cliente.
4. Dossiê em PDF e envio direto ao correspondente bancário.
5. Registro da origem do lead (Instagram, portal, feirão, indicação) e do anúncio.
6. Integração com portais de imóveis para atualizar o catálogo.

## Documentação

A documentação completa (funcionalidades, funcionamento, tecnologias, uso de IA no desenvolvimento, testes e limitações) acompanha a entrega:https://go.fliplink.me/view/AD3A729C-0588-4060-B0E0-0F1C0C43C78E .

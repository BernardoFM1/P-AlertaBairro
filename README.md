# Alerta Bairro

Rede comunitária de alertas hiperlocais sobre emergências climáticas em Volta Redonda, RJ. Moradores avisam e consultam alagamentos, falta de luz e quedas de árvores rua a rua, por WhatsApp, Telegram ou painel web.

## Como funciona

O morador relata uma ocorrência em linguagem natural. A inteligência artificial (Google Gemini) transforma a mensagem em um registro estruturado em tempo real, e regras determinísticas, sem IA, cuidam da confirmação e do encerramento das ocorrências. Tudo aparece em um painel público e acessível, com mapa e contexto meteorológico, e a previsão do tempo é identificada como informação externa.

## Tecnologias

- Front-end & API: Next.js 16 (App Router), React 19, TypeScript, Tailwind CSS
- Banco de Dados & Realtime: Supabase (PostgreSQL + RLS + CDC Realtime)
- Motor de Inteligência Artificial: Google Gemini API (gemini-3.1-flash-lite via @google/genai)
- Canais Conversacionais: WhatsApp Cloud API (Meta), Telegram Bot API e Simulador Demo integrado
- Testes Unitários: Vitest
- Mapa & Geocodificação: Leaflet + OpenStreetMap/Nominatim, com cache e fallback para o centróide do bairro
- Contexto Meteorológico: Open-Meteo, identificado visualmente como previsão externa

## Privacidade

Nenhum telefone é guardado em texto plano, apenas um hash com salt. O painel público lê somente dados anonimizados, protegidos por Row Level Security. O morador pode revogar o consentimento e apagar seus dados enviando o comando SAIR. A geocodificação remove o número da residência e envia ao provedor só a rua, o bairro e a cidade.

## Sobre o projeto

Criado para um hackathon. O código-fonte é privado.

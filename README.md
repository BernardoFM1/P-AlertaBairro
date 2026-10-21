# Alerta Bairro

Rede comunitária de alertas hiperlocais sobre emergências climáticas em Volta Redonda, RJ. Moradores avisam e consultam alagamentos, falta de luz e quedas de árvores rua a rua, por WhatsApp, Telegram ou painel web.

## Como funciona

O morador relata uma ocorrência em linguagem natural. A inteligência artificial (Google Gemini) transforma a mensagem em um registro estruturado em tempo real, e regras determinísticas, sem IA, cuidam da confirmação e do encerramento das ocorrências. Tudo aparece em um painel público e acessível, com mapa e contexto meteorológico, e a previsão do tempo é identificada como informação externa.

## Tecnologias

Next.js 16 (App Router), React 19, TypeScript e Tailwind CSS no front-end e na API. Supabase (PostgreSQL com RLS e Realtime) para os dados. Google Gemini para estruturar as mensagens. WhatsApp Cloud API, Telegram Bot API e um simulador de demonstração como canais de entrada. Leaflet com OpenStreetMap e Nominatim para o mapa, Open-Meteo para o contexto do tempo e Vitest para os testes.

## Privacidade

Nenhum telefone é guardado em texto plano, apenas um hash com salt. O painel público lê somente dados anonimizados, protegidos por Row Level Security. O morador pode revogar o consentimento e apagar seus dados enviando o comando SAIR. A geocodificação remove o número da residência e envia ao provedor só a rua, o bairro e a cidade.

## Sobre o projeto

Criado para um hackathon. O código-fonte é privado.

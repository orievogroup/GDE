# Arena Ao Vivo

App interativo para aulas/treinamentos ao vivo com suporte a 100+ participantes simultâneos.

## Acesso

- **Apresentador (criar/gerenciar):** `https://orievogroup.github.io/GDE/arena/arena.html`
- **Participante (entrar via QR ou link):** `?s=CODIGO` (gerado automaticamente)

**Senha padrão:** `Arena2026GDE`  
*(Pode ser alterada por navegador/dispositivo via interface)*

---

## Recursos

✅ **Participant Access** — QR Code + link compartilhável  
✅ **Live Counting** — Contador de participantes em tempo real  
✅ **Question Flow** — Enter key para avançar (apenas apresentador)  
✅ **Activity Types** — Quiz (multipla escolha), V/F (verdadeiro/falso), Word Cloud  
✅ **All Answered Notification** — Alerta sonoro quando todos responderam  
✅ **Scoring** — Acumular ou zerar pontos por atividade  
✅ **Single Response** — Uma resposta por pergunta (sem duplicatas)  
✅ **Final Ranking** — Ranking com top 3 destaque + export CSV  
✅ **Word Cloud** — Nuvem de palavras com tamanho dinâmico por frequência  
✅ **Session Branding** — Logo + cor customizável por sessão  
✅ **Theme Reuse** — Salvar temas reutilizáveis em localStorage  
✅ **Responsive Design** — Funciona em desktop, tablet, mobile  
✅ **Real-time Sync** — Firebase Realtime Database

---

## Como Criar Sessão

1. Abra `arena.html`
2. Digite a senha: `Arena2026GDE`
3. Clique **"+ Nova Sessão"**
4. Configure:
   - Nome da sessão
   - Logo (URL)
   - Cor principal
   - Modo de pontuação (acumular/zerar)
5. Adicione atividades (Quiz, V/F, ou Word Cloud)
6. Clique **"Criar Sessão"** → gera QR Code + link
7. Compartilhe QR ou link com participantes
8. Pressione **Enter** para avançar entre questões

---

## Participante — Como Entrar

1. Escaneie o QR Code **OU** abra o link compartilhado
2. Digite seu nome
3. Aguarde o apresentador iniciar
4. Responda as atividades conforme apareçam
5. Veja seu ranking final

---

## Firebase Configuration

**Projeto:** `dislub-equador`  
**Database URL:** `https://dislub-equador-default-rtdb.firebaseio.com`  
**Path:** `arena_v2/`

### Se Firebase ficar offline:

1. Acesse [console.firebase.google.com](https://console.firebase.google.com)
2. Selecione projeto `dislub-equador`
3. Vá para **Realtime Database → Rules**
4. Cole as regras:

```json
{
  "rules": {
    "arena_v2": {
      ".read": true,
      ".write": true
    }
  }
}
```

5. Clique **Publish**

---

## Storage (localStorage)

Cada navegador/dispositivo armazena:

- `arena_pwd` — Senha do apresentador
- `arena_themes` — Temas salvos
- `arena_pid_[sessionId]` — Seu ID de participante
- `arena_pname_[sessionId]` — Seu nome
- `arena_ans_[sessionId]_[activityIndex]` — Respostas já enviadas

---

## Tecnologias

- HTML5 + CSS3 (Montserrat font)
- Firebase Realtime Database
- QRCode.js (geração de QR)
- Web Audio API (notificações sonoras)
- localStorage (persistência)

---

## Limites de Uso

- **Firebase Spark Plan:** até 100 conexões simultâneas
  - Para 100+ usuários: upgrade para **Blaze Plan** (pague conforme uso)

---

## Próximas Melhorias

- [ ] Editor de atividades (drag-drop, templates)
- [ ] Relatórios detalhados por participante
- [ ] Suporte a imagens em opções de quiz
- [ ] Timer para cada pergunta
- [ ] Breakout rooms / Equipes
- [ ] Análise em tempo real (gráficos)
- [ ] Integração Google Sheets (logging automático)
- [ ] Múltiplos idiomas

---

## Suporte

- **Apresentador:** Alterar senha → Botão "Senha" em qualquer tela
- **QR/Link:** Copiar automaticamente ou manualmente da tela de espera
- **Conexão:** Veja o status (ponto verde = conectado, vermelho = sem conexão)

---

**Última atualização:** 2026-05-21  
**Versão:** Arena v2 (Realtime)

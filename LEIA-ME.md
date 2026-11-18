# Mestrado de RPG, versão com mesas

Arquivos:

- `mestrado-mesas.html`: o site inteiro (login, mesas, fichas, anotações, roteiro, dados).
- `firestore.rules`: as regras do banco. É isto que impede, de verdade, um Player de editar o que é do Mestre.

## Instalação (uns 10 minutos, grátis)

1. Entre em https://console.firebase.google.com e clique em **Criar projeto** (pode desligar o Google Analytics).
2. No menu **Build > Authentication**, clique em **Vamos começar** e ative o método **E-mail/senha**.
3. Em **Build > Firestore Database**, clique em **Criar banco de dados**, escolha o modo **produção** e uma região (por exemplo `southamerica-east1`).
4. Na aba **Regras** do Firestore, apague tudo, cole o conteúdo de `firestore.rules` e clique em **Publicar**.
5. Em **Configurações do projeto** (engrenagem) > **Seus apps**, clique no ícone `</>` (Web), registre o app e copie o bloco `firebaseConfig`.
6. Abra `mestrado-mesas.html` num editor de texto, ache o bloco `firebaseConfig` no começo do `<script>` e troque pelos seus valores.
7. Hospede o arquivo. Opções gratuitas: **Firebase Hosting**, **Netlify** (arrastar o arquivo no site) ou **GitHub Pages**.
8. Em **Authentication > Configurações > Domínios autorizados**, adicione o endereço onde o site ficou hospedado (o login só funciona nesse endereço). Abrir o arquivo direto do computador não serve para jogar em grupo, porque o link de convite precisa de um endereço público.

## Como funciona

- **Login:** e-mail e senha. Na primeira vez a pessoa escolhe Mestre ou Player (só define a tela inicial; a mesma conta pode mestrar uma mesa e jogar em outra).
- **Minhas mesas:** duas abas, "Mestrando" e "Jogando".
- **Convite:** só o criador da mesa gera o link (aba Mesa). Quem abre escolhe **Player** ou **NPC**; no NPC, escolhe qual NPC livre atuar. O mestre pode gerar outro link (o antigo deixa de valer) ou cancelar.
- **Player:** gira dados; edita nome, classe, raça, antecedente, alinhamento, história, aparência, personalidade, perícias e foto. Na criação escolhe até 3 itens iniciais. Atributos, vida, mochila, habilidades, magias, nível e XP ficam travados.
- **Mestre:** edita tudo da ficha, menos nome, classe, raça, antecedente e alinhamento. Nível e XP são dele.
- **NPC:** vê o nome, a imagem e a descrição do NPC, gira dados e tem anotações.
- **Anotações:** particulares de cada pessoa (nem o mestre lê as dos jogadores).
- **Roteiro:** só o mestre vê (inclui os segredos).

## Observações

- As regras de permissão valem no servidor, então não dá para burlar pelo navegador.
- Excluir uma mesa tira o acesso de todos; os dados antigos ficam inacessíveis no banco.
- O plano gratuito do Firebase (Spark) cobre com folga uma mesa de RPG.

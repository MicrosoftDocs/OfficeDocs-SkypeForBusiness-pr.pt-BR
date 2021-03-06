---
title: "Configurar o Skype for Business Online"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/16/2017
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- O365E_SkypeforBusinessON
- O365M_SkypeforBusinessON
- O365P_SkypeforBusinessON
ms.prod: office-online-server
localization_priority: Priority
ms.collection:
- Adm_O365_CommTopIssues
- Adm_O365_Setup
- Adm_Skype4B_Online
- Adm_Skype4B_Online_Top
ms.custom:
- Adm_O365_FullSet
- Alchemy
- DianeF_Adm_Simplified
- DianeF_Setup_HappyPath
- LeftNav_Adm_O365
- LIL_Placement
ms.assetid: 40296968-e779-4259-980b-c2de1c044c6e

description: "Learn to set up your domain, users, IM and presense for your organization to install Skype for Business. Also See how to set up dial-in conferencing, Cloud PBX and PSTN calling, and Skype Meeting broadcast. "
---

# Configurar o Skype for Business Online

Colaboradores: [![Diane Faigel](../images/e4ec7084-196e-4e04-bccc-e241da509abf.png)
  
](https://go.microsoft.com/fwlink/?linkid=847124)
  
Você deve ter permissões globais de administrador do Office 365 para configurar o Skype for Business. Se você tiver um firewall ou servidor proxy que restrinja o acesso a partes da Web, considere contratar um [parceiro da Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) para configurar o Skype for Business para você.
  
## Configurando o Skype

Parece que você precisa de ajuda para configurar o Skype com sua assinatura do Office 365. Você pode seguir as etapas [neste artigo](https://support.office.com/article/https://support.office.com/en-us/article/Set-up-Skype-for-Business-Online-40296968-e779-4259-980b-c2de1c044c6e.aspx#bkmk_more) para concluir a configuração.
  
## 1. Planejar para o Skype for Business

Se você tem o **[Office 365 Business Premium](https://products.office.com/en-us/business/office-365-business-premium)** ou o **Business Essentials**, pode usar o Skype for Business para fazer chamadas online para outras pessoas da sua empresa que estão na sua assinatura. Por exemplo, se a sua empresa tem 10 pessoas, vocês podem[Começar a usar o Skype for Business para mensagens instantâneas e reuniões online](https://support.office.com/article/cc05afa6-1894-4a82-9dd9-6222061f50fd) entre si, bem como[Meetings with Skype for Business](https://support.office.com/article/2eed8424-581a-4497-b505-c08c152e5851) usando o Skype for Business após executar as etapas 2 a 6 abaixo. E você também pode[Configurar uma reunião do Skype for Business no Outlook](https://support.office.com/article/b8305620-d16e-4667-989d-4a977aad6556#bkmk_OWA) para reuniões online.
  
Se você quer usar o Skype for Business para fazer e receber **chamadas** de pessoas *externas*  à sua empresa:
  
- **Opção 1. Usar o [aplicativo Skype](https://www.skype.com/)** gratuito. Se você tem uma empresa bem pequena (por exemplo, uma ou duas pessoas), usar o aplicativo Skype é a melhor solução. As chamadas nacionais e internacionais são mais baratas. Você ainda pode realizar chamadas em conferência, fazer chamadas de vídeo e compartilhar sua área de trabalho para apresentações.[Confira as tarifas e opções de pagamento](https://secure.skype.com/en/calling-rates?wt.mc_id=legacy&amp;expo365=bundled).
    
- **Opção 2. Atualize seu plano e compre o Sistema de Telefonia Office 365 e o Plano de Chamadas Office 365**. A maneira mais fácil de descobrir quanto isso custa e depois migrar é[Contatar o suporte do Office 365 para empresas - Ajuda para Administradores](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) e deixar que nossa equipe prepare tudo para você.
    
Para saber mais, consulte [Planejar a configuração do Office 365 para empresas](https://support.office.com/article/eb926624-018b-4486-bf11-5fba6ee4d645#bkmk_skype).
  
## 2. Entrar no Office 365
<a name="bkmk_signin"> </a>

O Skype for Business Online faz parte do pacote de serviços do Office 365. Para configurar o Skype for Business Online, você precisa entrar no Office 365. Veja como fazer isso:
  
1. Localize sua identificação de usuário do Office 365 (por exemplo,  *rob@fourthcoffee.com*  ). Você recebeu um email da Equipe do Microsoft Online Services contendo a identificação de usuário do Office 365 que você criou quando adquiriu o Skype for Business Online. O email tem esta aparência:
    
    ![Um exemplo de email de boas-vindas que você recebe após se inscrever no Skype for Business Online. Ele inclui a ID de usuário do Office 365.](../images/977c5c96-29c5-40c0-a4c4-1ba66ba3a1fb.png)
  
2. Acesse [https://portal.office.com/](https://go.microsoft.com/fwlink/p/?linkid=402333) e insira sua identificação de usuário e senha do Office 365. Depois de entrar, você verá o Centro de administração do Office 365:
    
    ![Um exemplo da aparência do centro de administração do Office 365 quando você tem um plano do Skype for Business Online.](../images/ed1d9906-e717-450b-81a3-ce6679bd1be1.png)
  
## 3. Configurar seu domínio e usuários
<a name="bkmk_users"> </a>

Agora que está conectado ao Office 365, você pode configurar seu domínio e as pessoas em sua organização para usar o Skype for Business Online.
  
1. [Verificar e gerenciar o seu domínio no Office 365](https://support.office.com/article/6383f56d-3d09-4dcb-9b41-b5f5a5efd611): use o assistente de instalação do Office 365 para configurar seu domínio personalizado (como  *fourthcoffee.com*  ) com o Office 365. **Por padrão, o assistente de instalação do Office 365 inclui a configuração do Skype for Business Online e a criação das IDs de usuário do Skype for Business.** Se já usou o assistente para configurar o seu domínio para o Office 365, você concluiu esta etapa.
    
2. [Verificar suas conexões de domínio e DNS](https://support.office.com/article/2b54e1b0-47a7-4018-a1e4-c2b924e7c5a0 .aspx): use nossa ferramenta de solução de problemas com domínios para verificar se as configurações de domínio e DNS estão corretas. Esse procedimento ajudará a entender eventuais problemas de configuração no futuro, já que você poderá eliminar as configurações de DNS como origem de futuros problemas. 
    
3. [URLs e intervalos de endereços IP do Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_LYO): a maioria das pequenas empresas não precisa realizar esta etapa. **Mas se você tiver um servidor proxy ou firewall que restringe o acesso a partes da Web**, deverá criar regras para permitir acesso aos pontos de extremidade do Skype for Business Online. Esta é uma etapa avançada, que pode ser realizada com mais eficiência por alguém que tenha experiência na configuração de firewalls e servidores proxy. Caso não tenha feito isso antes, considere a possibilidade de contratar um[parceiro da Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) para configurar o Skype for Business para você.
    
## 4. Configurar mensagens instantâneas e presença em sua organização
<a name="bkmk_IM"> </a>

Mensagens instantâneas (IM) e presença ([Controlar o acesso às suas informações de presença no Skype for Business](https://support.office.com/article/fea86e34-60cf-4dd0-bfb2-169a42afd92c#bkmk_presence)) são recursos básicos disponibilizados com o Skype for Business. Por padrão, as pessoas de sua empresa podem usar o Skype e trocar mensagens instantâneas entre si.
  
1. **Escolha com quem mais seus usuários do Skype for Business podem se comunicar:**
    
  - [Permitir que os usuários entrem em contato com usuários externos do Skype for Business](allow-users-to-contact-external-skype-for-business-users.md) Você *e*  as outras empresas precisarão configurar seus sistemas.
    
    **IMPORTANTE**: se sua empresa tem dois domínios, como rob@contosowest.com e ina@contosoeast.com, você deverá executar esta etapa para que todos os seus usuários possam se comunicar uns com os outros.
    
  - [Permitir que os usuários do Skype for Business adicionem contatos do Skype](let-skype-for-business-users-add-skype-contacts.md) fora da sua empresa
    
2. **Escolha quem vê se seus colegas de trabalho estão online:** o recurso de presença mostra quem está online e qual o status: disponível, ocupado, ausente ou apresentando.
    
    ![An example of a person's online status with a personal message.](../images/ab6c10b4-6ad5-453c-bf0e-459b977b6e23.png)
  
    Você pode escolher as configurações padrão para todas as pessoas em sua empresa: 
    
  - Exibir automaticamente a presença online de uma pessoa para todos na organização
    
  - Exibir a presença online de uma pessoa apenas para seus contatos
    
Para obter instruções, veja [Configuração de presença do Skype for Business Online](configure-presence-in-skype-for-business-online.md).
  
## 5. Baixar e instalar o Skype for Business
<a name="bkmk_download"> </a>

Para usar o Skype for Business em seu PC, Mac ou dispositivo móvel, você e outras pessoas em sua empresa precisam primeiramente baixar e instalar o Skype for Business em seus dispositivos.
  
- [Como instalar o Skype for Business](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb): instruções sobre como baixar o aplicativo do portal do Office 365 e instalá-lo em seu PC ou Mac.
    
- [Implantar o Cliente Skype for Business no Office 365](deploy-the-skype-for-business-client-in-office-365.md) : instruções sobre como implantar o aplicativo em uma grande corporação.
    
- [Como instalar o Skype for Business](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb): baixe, instale e entre no Skype for Business em dispositivos Android, iOS e Windows Phone.
    
- [Ativar ou desativar notificações do telefone celular](turn-on-or-off-mobile-phone-notifications.md) : se você tem o Skype for Business instalado em um dispositivo móvel, você e outras pessoas em sua empresa podem receber alertas sobre mensagens instantâneas recebidas e perdidas.
    
## 6. Testar para verificar se tudo está funcionando
<a name="bkmk_test"> </a>

Primeiramente, teste se você e outras pessoas em sua empresa podem [Entrar e sair do Skype for Business](https://support.office.com/article/8abed4b3-ac48-493e-9d76-0e10140e9451). Verifique se você pode enviar mensagens instantâneas para outras pessoas, ver a presença delas e tente fazer uma reunião rápida.
  
Em caso de problemas, faça o seguinte:
  
- [Precisa de ajuda para entrar no Skype for Business?](https://support.office.com/article/448b8ea7-5b33-444a-afd4-175fc9930d05) de problemas comuns ao entrar.
    
- [Contatar o suporte do Office 365 para empresas - Ajuda para Administradores](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b). Estamos aqui para ajudar!
    
## Você deseja configurar outros recursos disponíveis?
<a name="bkmk_more"> </a>

Antes de configurar mais recursos, verifique se você tem licenças para eles. [Skype para Business e Teams Microsoft complemento licenciamento](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
### Configurar a Audioconferência

Ocasionalmente, as pessoas em sua organização precisarão usar um telefone para participar de uma reunião. O Skype for Business inclui o recurso de audioconferência exatamente para essas ocasiões! As pessoas podem participar de uma reunião do Skype for Business usando um telefone em vez de usar o aplicativo Skype for Business em um dispositivo móvel ou computador.
  
Para obter instruções de instalação passo a passo, consulte [Configurar conferência de áudio para o Skype for Business e Teams da Microsoft](../audio-conferencing-in-office-365/set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md) no Office 365.
  
### Configurar o Sistema de Telefonia e os Planos de Chamada no Office 365

O recurso Sistema de Telefonia do Office 365 fornece um sistema de telefonia para sua empresa. As chamadas para outras pessoas que usam o Skype for Business na sua organização são gratuitas, e seus funcionários podem receber mensagens de voz uns dos outros e de chamadores externos. Veja o que você obtém com o Sistema de Telefonia.
  
Quando você adiciona o serviço Plano de Chamadas, seus funcionários recebem um número de telefone principal no Skype for Business. Eles podem fazer e receber chamadas telefônicas fora da empresa. Podem também fazer chamadas de voz por telefones VoIP, computadores e dispositivos móveis. E, em casos de emergência, podem ligar para o número local destinado a esse fim para obter ajuda.
  
Para instruções de configuração passo a passo, veja Configurar Planos de Chamada.
  
### Configurar o Transmissão de Reunião do Skype

O Transmissão de Reunião do Skype é um recurso que permite produzir, hospedar e transmitir reuniões com até 10.000 participantes. **Para saber mais sobre como ele funciona, veja [O que é uma Transmissão de Reunião do Skype?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)**
  
Veja aqui uma visão geral das etapas para configurar o Transmissão de Reunião do Skype:
  
1. [Atribuir ou remover licenças de assinatura no Office 365](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc): atribua licenças do **Skype for Business Online** ou do **Plano Empresarial** a todas as pessoas que vão **organizar** uma reunião de transmissão.
    
2. [Habilitar a Transmissão de Reunião do Skype](../set-up-your-network-for-skype-meeting-broadcast/enable-skype-meeting-broadcast.md) : por padrão, este recurso não está habilitado. Depois que você ativá-lo, os usuários poderão organizar reuniões de transmissão com outras pessoas na sua organização.
    
3. [Configurar a rede para a Transmissão de Reunião do Skype](../set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast.md) : se quiser organizar webinars e outras transmissões com participantes fora da sua organização, você precisará configurar sua rede.
    
4. [Agendar uma Transmissão de Reunião do Skype](https://support.office.com/article/c3995bc9-4d32-4f75-a004-3bc5c477e553) e pedir que um[Participar de uma Transmissão de Reunião do Skype](https://support.office.com/article/14689da0-821d-48d4-9035-ea762de80ebe): verifique se as reuniões de transmissão estão funcionando ao agendar uma Transmissão de Reunião do Skype em  *https://portal.broadcast.skype.com*  . Em seguida, peça que alguém tente ingressar na reunião.
    
## Saiba mais sobre os requisitos de conectividade de rede
<a name="bkmk_more"> </a>

A qualidade do áudio, vídeo e compartilhamento de aplicativos no Skype for Business é muito afetada pela qualidade da conectividade de rede de ponta a ponta. Para obter uma experiência ideal, é importante assegurar que exista uma conexão de alta qualidade entre a rede de sua empresa e o Skype for Business Online. Para obter informações sobre rede e ajuste, veja [Ajustar o desempenho do Skype for Business Online](https://support.office.com/article/beec23c2-c5d6-4e84-a8af-e82aefca7802).
  
## Terminou a configuração? Introdução ao Skype for Business
<a name="bkmk_more"> </a>

[Descubra o Skype for Business](https://support.office.com/article/8a3491a3-c095-4718-80cf-cbbe4afe4eba): confira esta lista de tópicos de treinamento para ajudar você a começar rapidamente!
  
[Iniciar uma chamada em conferência no Skype for Business](https://support.office.com/article/8dc8ac52-91ac-4db9-8672-11551fdaf997)
  
[Definir opções de Dispositivo de Vídeo no Skype for Business](https://support.office.com/article/d09017c0-deba-4f6c-a122-9eca6604f50c)
  
[Fazer e receber uma chamada de vídeo usando o Skype for Business](https://support.office.com/article/abf62493-670f-4b0d-b2cf-fe03b49caf42)
  
## 
<a name="bkmk_more"> </a>

||
|:-----|
|![O ícone pequeno do LinkedIn Learning.](../images/7e5cb7c8-dc66-4c9a-a16d-a30f10a970bd.png) **Novo no Office 365?**         Descubra cursos de vídeo gratuitos para **Administradores do Office 365 e profissionais de TI**, disponibilizados pelo LinkedIn Learning. |
   
## Tópicos Relacionados
<a name="bkmk_more"> </a>

[Planejar a conectividade híbrida entre o Skype for Business Server e o Skype for Business Online](https://go.microsoft.com/fwlink/p/?linkid=400791)
  


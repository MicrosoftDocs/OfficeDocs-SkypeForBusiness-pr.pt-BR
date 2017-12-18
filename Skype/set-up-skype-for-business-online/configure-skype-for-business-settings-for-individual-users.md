---
title: "Administradores Definir as configurações do Skype for Business para usuários individuais"
ms.author: TONYSMIT
author: tonysmit
manager: scotv
ms.date: 11/9/2017
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.lync.lac.UsersExternalAccess
- ms.lync.lac.UsersGeneralOptions
- ms.lync.lac.UsersLyncToPhoneMoreInfo
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
- LIL_Placement
ms.assetid: 77b26eac-8228-4161-ba9f-733b187bd836

description: "Learn how to change the Skype for Business settings for individual users such as: Audio and video conferencing, recording of calls and meetings. "
---

# Administradores: Definir as configurações do Skype for Business para usuários individuais

> [!IMPORTANT]
> Este artigo foi traduzido por um sistema de tradução automática, leia o aviso de isenção de responsabilidade.  
  
Este artigo explica como administradores configurar o Skype for Business para um pequeno número de usuários. Para executar essas etapas em massa, podemos adicionei links para cmdlets do Windows PowerShell, que você pode usar.
  
Para permitir (ou impedir) que todos na empresa se comuniquem com pessoas externas, veja:
  
- [Permitir que os usuários entrem em contato com usuários externos do Skype for Business](allow-users-to-contact-external-skype-for-business-users.md) : você pode permitir que sua organização use recursos avançados do Skype for Business (compartilhar áreas de trabalho, procurar pessoas online) para se comunicar com pessoas em uma determinada empresa confiável (federada). Explica também como bloquear a comunicação com domínios específicos.
    
- [Permitir que os usuários do Skype for Business adicionem contatos do Skype](let-skype-for-business-users-add-skype-contacts.md) . Você pode permitir que sua organização use o Skype for Business para procurar usuários do aplicativo gratuito Skype e enviar mensagens instantâneas para eles.
    
## Definir configurações gerais para um usuário
<a name="__toc325019204"> </a>

Você deve ter o [Tudo sobre as funções de administrador do Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) para executar essas etapas.
  
1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Escolha **Centros de administração** > **Skype for Business**. 
    
3. Escolha **Usuários**.
    
    ![In the Skype for Business admin center, choose Users.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. Selecione quais usuários você deseja editar: 
    
5. No painel direito, escolha **Editar**.
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. Na página de opções **Geral**, marque ou desmarque a caixa de seleção ao lado dos recursos que você quer alterar e clique em **Salvar**.
    
|**Opção**|**Detalhes**|
|:-----|:-----|
|Áudio e vídeo em HD  <br/> |Permita que esta pessoa grave reuniões de áudio, reuniões de áudio e vídeo e áudio, ou não permita que agendem nenhuma reunião (nenhum).  <br/> |
|Gravar conversas e reuniões  <br/> |Escolha o que esta pessoa tem permissão para gravar.  <br/> Esta opção não está disponível com Skype for Business Basic.  <br/> |
|Para fins de conformidade, desligue os recursos não arquivados  <br/> | Selecione esta opção se você for obrigado legalmente a preservar informações armazenadas eletronicamente. <br/>  Selecionar essa opção desativa recursos que não são capturados quando você tem um[Bloqueio In-loco](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx) configurado no Centro de administração do Exchange. Ele desativa os seguintes recursos: <br/>  Transferência de arquivos usando mensagens de chat <br/>  Páginas do OneNote compartilhadas <br/>  Anotações do PowerPoint <br/> |
   
Para definir essas configurações em massa, use o PowerShell. Consulte [políticas de gerenciamento no Skype for Business Online](https://technet.microsoft.com/en-us/library/dn362826%28v=ocs.15%29.aspx).
  
## Bloquear comunicações externas
<a name="__toc325019206"> </a>

Depois de [Permitir que os usuários do Skype for Business adicionem contatos do Skype](let-skype-for-business-users-add-skype-contacts.md) para todos na sua empresa, você pode bloquear seletivamente as comunicações externas de indivíduos específicos usando estas etapas.
  
1. Escolha **usuários**, selecione os usuários cujas configurações você deseja desabilitar e clique em seguida **Editar**![Editar](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).
    
2. Escolha **Comunicações externas** e desmarque as opções conforme apropriado:
    
  - **Skype externo para usuários de negócios**: desmarque esta caixa se não quiser que o usuário sejam capazes de se comunicar com usuários de Skype for Business em domínios federados.
    
  - **Os usuários externos do Skype**: desmarque esta caixa se não quiser que o usuário sejam capazes de se comunicar com pessoas que estão usando o aplicativo gratuitoSkype.
    
3. Clique em **Salvar**.
    
Para definir essas configurações em massa, use o PowerShell. Consulte [gerenciamento de comunicações no Skype for Business Online com usuários de fora e organizações](https://technet.microsoft.com/en-us/library/dn362813%28v=ocs.15%29.aspx).
  
## Editar configurações de conferência de áudio para um usuário
<a name="__toc314837483"> </a>

1. Escolha **usuários**, selecione o usuário cujas configurações de conferência de áudio que você quer editar, e escolha **Editar**![Editar](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).
    
2. Escolha **a conferência de áudio**, selecione seu provedor de audioconferência, digite ou mude as informações solicitadas e clique em **Salvar**.
    
|**Configuração de conferência de áudio**|**Descrição**|
|:-----|:-----|
|**Nome do provedor** <br/> |Escolha seu provedor da lista.  <br/> |
|**Número de chamada tarifada** (obrigatório) <br/> |Para um ACP de terceiros, esses números de telefone são aquelas que você recebeu do provedor de audioconferência. Se o usuário estiver usando o Microsoft como provedor de audioconferência, esses serão números definidos a ponte de conferência de áudio. Formate números como deseja que eles apareçam em Skype for Business e Teams da Microsoft solicitações de reunião.  <br/> |
|**Número de chamada gratuita** <br/> |Para um ACP de terceiros, esses números de telefone são aquelas que você recebeu do provedor de audioconferência. Se o usuário estiver usando o Microsoft como provedor de audioconferência, esses serão números definidos a ponte de conferência de áudio. Formate números como deseja que eles apareçam em Skype for Business e Teams da Microsoft solicitações de reunião.  <br/> |
|**PIN e ID de conferência** (obrigatório) <br/> |O código PIN de participante ou conferência, usado para ingressar nas reuniões agendadas por esse usuário e são fornecidas de um provedor de audioconferência terceirizado. Se o usuário estiver usando o Microsoft como provedor de audioconferência, isso não será necessário.  <br/> |
   
Para definir essas configurações em massa, use o PowerShell. Consulte [Definir os números de telefone de conferência de áudio para organizadores incluídas na convites de reunião](../audio-conferencing-in-office-365/set-the-audio-conferencing-phone-numbers-for-meeting-organizers-that-are-include.md).
  
## 
<a name="__toc314837483"> </a>

||
|:-----|
|![O ícone pequeno do LinkedIn Learning.](../images/7e5cb7c8-dc66-4c9a-a16d-a30f10a970bd.png) **Novo no Office 365?**         Descubra cursos de vídeo gratuitos para **Administradores do Office 365 e profissionais de TI**, disponibilizados pelo LinkedIn Learning. |
   
## Tópicos Relacionados
<a name="__toc314837483"> </a>

[Configurar o Skype for Business Online](set-up-skype-for-business-online.md)[Skype para Business e Teams Microsoft complemento licenciamento](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Aviso de Isenção de Tradução Automática**: Este artigo foi traduzido por computador, sem intervenção humana. A Microsoft oferece essas traduções automáticas para ajudar as pessoas que não falam inglês a aproveitar os textos escritos sobre produtos, serviços e tecnologias da Microsoft. Como este artigo foi traduzido automaticamente, é possível que contenha erros de vocabulário, sintaxe ou gramática. 
  


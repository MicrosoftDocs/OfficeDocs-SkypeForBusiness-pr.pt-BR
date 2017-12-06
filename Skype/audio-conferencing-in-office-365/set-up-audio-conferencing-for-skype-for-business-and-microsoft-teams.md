---
title: "Configurar conferência de áudio para o Skype for Business e Teams da Microsoft"
ms.author: TONYSMIT
author: tonysmit
manager: scotv
ms.date: 11/22/2017
ms.audience: Admin
ms.topic: article
f1_keywords:
- O365P_DialInConfDesc
ms.prod: office-online-server
localization_priority: Normal
ms.collection:
- Adm_Skype4B_Online
- Adm_Skype4B_Online_Top
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
- LIL_Placement
- Strat_SB_PSTN
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9

description: "Learn how to set up dial-in or audio conferencing (PSTN Conferencing) for the people in your business who need to join conference calls using a phone. "
---

# Configurar conferência de áudio para o Skype for Business e Teams da Microsoft

> [!IMPORTANT]
> Este artigo foi traduzido por um sistema de tradução automática, leia o [aviso de isenção de responsabilidade](d01954f1-4f37-4cf5-a636-20039e5c59e9.md#MT_Footer). Para sua referência, veja a versão em inglês deste artigo [aqui](https://support.office.com/en-us/article/d01954f1-4f37-4cf5-a636-20039e5c59e9). 
  
Às vezes, pessoas em sua organização precisa usar um telefone para ligar para uma reunião. Skype for Business e Teams da Microsoft incluem o recurso de conferência de áudio para apenas essa situação! As pessoas podem ligar para Skype for Business ou reuniões de Teams da Microsoft usando um telefone, em vez de usar o Skype for Business ou o aplicativo de Teams da Microsoft em um PC ou dispositivo móvel.
  
Você só precisa configurar as conferências de áudio para as pessoas que pretende agendar ou conduzir reuniões. Participantes da reunião que discam não é necessário qualquer licenças atribuídas a eles ou outra instalação.
  
Para perguntas frequentes sobre a conferência de áudio, consulte [Áudio perguntas comuns de conferência](audio-conferencing-common-questions.md).
  
## Etapa 1: comprar e atribuir licenças
<a name="__top"> </a>

Você deve ser um [Tudo sobre as funções de administrador do Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) para executar esta etapa.
  
1. Descubra se conferência de áudio no Office 365 está disponível em seu país/região. [Países e disponibilidade de região para conferência de áudio e planos de chamada](../countries-and-region-availability-for-audio-conferencing-and-calling-plans/countries-and-region-availability-for-audio-conferencing-and-calling-plans.md).
    
2. Saiba quais licenças que você precisará comprar para conferência de áudio e quanto eles custa. Consulte o [Skype para Business e Teams Microsoft complemento licenciamento](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)e comprar licenças.
    
3. [Atribuir ou remover licenças de assinatura no Office 365](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) você comprou com as pessoas em sua organização estão indo para reuniões de cronograma ou cliente potencial.
    
4. Se você adquiriu licenças do suplemento de **Conferência de áudio** e licenças de créditos de comunicações, atribuí-los também. Para obter instruções, consulte[Atribuir Skype para Business e Teams Microsoft licenças](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).
    
## Etapa 2: Decidir no seu provedor de audioconferência
<a name="__top"> </a>

Um provedor de audioconferência fornece uma  *ponte de conferência de áudio*  . A ponte de conferência define seus números de discagem, pinos e IDs de conferência para reuniões. Decida se usar um provedor de audioconferência terceirizado ou Microsoft:
  
> [!NOTE]
> Usuários de Teams Microsoft não poderá usar um provedor de audioconferência terceirizado. 
  
- **Microsoft como seu provedor de audioconferência**: se você quiser a solução mais fácil para conferência de áudio, escolha Microsoft como seu provedor de audioconferência.
    
- **Terceiro como seu provedor de audioconferência**: se você estiver em um país onde audioconferência no Office 365 não está disponível, a qualidade do serviço não é ótima devido a sua localização, ou você tem um contrato existente, escolha um áudio de terceiros provedor de conferência. Para encontrar um provedor, vá para o **[Microsoft PinPoint](http://go.microsoft.com/fwlink/?LinkId=797530)**.
    
> [!TIP]
> Em sua organização, você pode ter algumas pessoas que usam a Microsoft como seu provedor de audioconferência e outras pessoas que usam um provedor de terceiros. Mas esta será mais complicada para configurar e gerenciar. 
  
Para obter uma comparação detalhada entre a Microsoft como seu provedor de áudio e um provedor de terceiros, consulte [Comparar os provedores de conferência de áudio](compare-audio-conferencing-providers.md).
  
## Etapa 3: Atribuir o provedor de conferência de áudio pessoas levam ou agendar reuniões
<a name="__top"> </a>

Agora que você decidiu no seu provedor de conferência de áudio, você precisa atribuir o provedor para as pessoas em sua organização que avanço ou agendar reuniões. Siga um destes procedimentos:
  
- [Atribuir a Microsoft como provedor de audioconferência](assign-microsoft-as-the-audio-conferencing-provider.md) .
    
- [Atribuir um terceiro como provedor de audioconferência](assign-a-third-party-as-the-audio-conferencing-provider.md) .
    
## Etapa 4: Configurar convites de reunião
<a name="__top"> </a>

As etapas a seguir são **opcionais**, mas muitos dos administradores optam por seguí-las:
  
1. [Personalizar convites de reunião](../set-up-skype-for-business-online/customize-meeting-invitations.md) . Os números de discagem definidos para o usuário serão adicionados automaticamente aos convites da reunião enviados aos participantes. No entanto, é possível adicionar os seus próprios links de ajuda e jurídicos, uma mensagem de texto e um pequeno logotipo da empresa.
    
2. [Definir os números de telefone de conferência de áudio para organizadores incluídas na convites de reunião](set-the-audio-conferencing-phone-numbers-for-meeting-organizers-that-are-include.md) . Este é o número telefônico que aparecerá na reunião agendada pelo usuário.
    
3. [Definir idiomas do atendedor automático para conferência de áudio](set-auto-attendant-languages-for-audio-conferencing.md) que usa o atendedor automático da conferência de áudio para saudar um chamador quando eles discarem para um número de telefone de audioconferência. Esta etapa aplica-se somente se você estiver usando o Microsoft como seu provedor de áudio.
    
4. [Definir o tamanho do PIN para reuniões de conferência de áudio](set-the-length-of-the-pin-for-audio-conferencing-meetings.md) .
    
> [!NOTE]
> O recurso ainda não está disponível para os clientes que usam o Office 365 operado pela 21Vianet na China. Para saber mais, consulte [Learn about Office 365 operated by 21Vianet](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE). 
  
||
|:-----|
|![O ícone pequeno do LinkedIn Learning.](../images/7e5cb7c8-dc66-4c9a-a16d-a30f10a970bd.png) **Novo no Office 365?**         Descubra cursos de vídeo gratuitos para **Administradores do Office 365 e profissionais de TI**, disponibilizados pelo LinkedIn Learning. |
   
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Aviso de Isenção de Tradução Automática**: Este artigo foi traduzido por computador, sem intervenção humana. A Microsoft oferece essas traduções automáticas para ajudar as pessoas que não falam inglês a aproveitar os textos escritos sobre produtos, serviços e tecnologias da Microsoft. Como este artigo foi traduzido automaticamente, é possível que contenha erros de vocabulário, sintaxe ou gramática. 
  
## Consulte Também
<a name="MT_Footer"> </a>

#### 

[Áudio perguntas comuns de conferência](audio-conferencing-common-questions.md)
  
[Configurar o Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[Números de telefone para conferência de áudio](phone-numbers-for-audio-conferencing.md)
  
[Definir opções de reuniões online e chamadas em conferência](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)


---
title: "Números de telefone para conferência de áudio"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/21/2017
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- LIL_Placement
- Strat_SB_PSTN
ms.assetid: 95a08f84-04e5-4f72-88a8-d6472a7c89d7

description: "Learn what countries and regions have dial-in conferencing numbers, and how they are automatically assigned."
---

# Números de telefone para conferência de áudio

> [!IMPORTANT]
> Este artigo foi traduzido por um sistema de tradução automática, leia o [aviso de isenção de responsabilidade](95a08f84-04e5-4f72-88a8-d6472a7c89d7.md#MT_Footer). Para sua referência, veja a versão em inglês deste artigo [aqui](https://support.office.com/en-us/article/95a08f84-04e5-4f72-88a8-d6472a7c89d7). 
  
Quando você estiver configurando ** Conferências de áudio** do Skype for Business e Teams Microsoft, números de discagem são atribuídos automaticamente à sua organização. Você pode ver os números de telefone atribuídos a sua ponte de conferência de áudio indo para o **Skype para o Centro de administração de negócios** > **audioconferência** > **ponte da Microsoft**. Consulte [Ver uma lista de números de conferência de áudio](see-a-list-of-audio-conferencing-numbers.md).
  
> [!NOTE]
> Não há um recurso que contém uma lista de todos os números de discagem para conferência de áudio. Se você está procurando para ver se há números de discagem disponíveis em sua área ou país/região, usar o **Skype para o Centro de administração de negócios** > **voz** > **Números de telefone**, clique em **Adicionar** **Novos números de serviço**. Use as listas de **País/região**, estado/região e **cidade** para filtrar sua pesquisa.> Além disso, se você estiver procurando por números de serviço gratuito de Chamada Tarifada, selecionar a **ligação gratuita** do **estado/região** lista.
  
## Cobertura de conferência de áudio e preços

Para obter uma lista completa de todos os países/regiões e cidades onde conferências de áudio estiver disponível, consulte [A Conferência PSTN com números de telefone está disponível em meu país ou minha região?](https://support.office.com/article/1096d81e-7e14-488c-95d8-b8322e39c059).
  
[Preço para conferência de áudio](https://products.office.com/en-us/skype-for-business/audio-conferencing#Requirements)
  
## Números de telefone de discagem em um convite de reunião

Quando um Skype for Business Online ou Teams Microsoft usuário agenda uma reunião no Outlook ou no Outlook Web App, o número de audioconferência padrão que é definido para o usuário está incluído no convite da reunião. Se você quiser selecionar um número padrão diferente para um ou mais usuários, é possível mudar indo para o **Skype para o Centro de administração de negócios** > **audioconferência** > **usuários**. Consulte [Definir os números de telefone de conferência de áudio para organizadores incluídas na convites de reunião](set-the-audio-conferencing-phone-numbers-for-meeting-organizers-that-are-include.md).
  
Outros números de discagem podem ser vistos clicando no link **Localizar um número local** no convite da reunião.
  
## Números de discagem configurar em uma ponte de conferência de áudio

Há dois tipos de números de telefone de conferência de áudio que podem ser atribuídos a sua ponte de conferência: **compartilhado** e **dedicada**. Os dois tipos desses números podem ser usados por qualquer chamador para ingressar em reuniões de áudio que estão sendo mantidos em sua organização.
  
 **Dedicada números de telefone** são os números de telefone que estão disponíveis somente para usuários de sua organização. Você pode alterar os idiomas que serão usados quando alguém chama um desses números.
  
 **Números de telefone de compartilhado** são esses números de telefone que podem ser compartilhados com outras organizações do Office 365. Você não pode alterar os idiomas que serão usados quando alguém chama um desses números.
  
Enquanto o número de audioconferência padrão atribuída a um organizador só é incluído no convite da reunião, um chamador pode usar qualquer um dos números de telefone que são atribuídos a sua ponte de conferência para ingressar em uma reunião. Lista de números de telefone que podem ser usadas para participar de uma reunião está disponível usando o link **Localizar um número local** que está incluído em cada convite de reunião.
  
## Atribuído automaticamente os números de telefone de conferência de áudio

Compartilhado telefone de audioconferência números são automaticamente atribuídos a organizações quando estão habilitados para conferência de áudio. Quando os números de telefone são atribuídos, um número de telefone é atribuído como o número de telefone padrão da ponte de conferência. O número de telefone atribuído como o número padrão de ponte será um partir do país/região da organização.
  
> [!NOTE]
> O local de país ou região da sua organização pode ser encontrado entrar para o **Centro de administração do Office 365** e procurando sob **Perfil da organização**. 
  
> [!CAUTION]
> Devido a disponibilidade limitada dos números de telefone de Chamada Tarifada em Venezuela, Indonésia e Emirados Árabes Unidos (Emirados Árabes Unidos), as organizações esses países/regiões não possui um número de Chamada Tarifada de conferência de áudio automaticamente atribuído a eles. Números de chamada gratuita desses locais estão disponíveis dependendo do estoque disponível. 
  
Números de telefone de audioconferência dedicado são números de serviço que você possa acessá-lo e depois atribuir a sua organização. Números de serviço podem ser encontrados usando o **Skype para o Centro de administração de negócios**. Para obter detalhes, consulte [Obtendo números telefônicos de serviço do Skype for Business](../what-is-phone-system-in-office-365/getting-service-phone-numbers-for-skype-for-business-and-microsoft-teams.md).
  
Para ver uma lista desses países/regiões que têm números de telefone atribuídos automaticamente para as organizações, consulte [Países e disponibilidade de região para conferência de áudio e planos de chamada](../countries-and-region-availability-for-audio-conferencing-and-calling-plans/countries-and-region-availability-for-audio-conferencing-and-calling-plans.md).
  
## O que mais você deve saber?

- Para ver a lista de idiomas com suporte para conferência de áudio, consulte [Idiomas com suporte de conferência de áudio](audio-conferencing-supported-languages.md).
    
- Você pode usar o cmdlet [Get-Csonlinedialinconferencingservicenumberhttp](https://go.microsoft.com/fwlink/?LinkId=617691) para ver os números de telefone dedicado para conferência de áudio para sua empresa.
    
- Você pode usar o cmdlet [Get-Csonlinedialinconferencinglanguagessupportedhttp](https://go.microsoft.com/fwlink/?LinkId=617684) para ver os idiomas que podem ser definidos em um número de telefone de discagem dedicado.
    
- Você pode definir idiomas até 4 para cada número de telefone de audioconferência: um primário e três secundários. E você também pode definir idiomas em um número de telefone de audioconferência dedicado.
    
- Para definir o número de discagem para um usuário, consulte [Definir os números de telefone de conferência de áudio para organizadores incluídas na convites de reunião](set-the-audio-conferencing-phone-numbers-for-meeting-organizers-that-are-include.md).
    
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

[Conferência discada no Office 365](../misctopics/dial-in-conferencing-in-office-365.md)


---
title: Atribuir, alterar ou remover o número de telefone de um usuário
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 91089761-cb87-4119-885b-3713840dd9f7
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: Saiba como atribuir, alterar ou remover um número de telefone comercial para suas equipes ou usuários do Skype for Business para que empresas e clientes externos possam fazer chamadas.
ms.openlocfilehash: f9792edf76d5d86a562516aa620bfbb62d26fdd9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286281"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user"></a>Atribuir, alterar ou remover o número de telefone de um usuário

Ao configurar planos de chamada no Office 365, você atribui números de telefone a seus usuários. 

No cliente do Microsoft Teams, os números de telefone atribuídos podem ser visualizados clicando em **Chamadas**.

![Número de telefone do usuário exibido no Microsoft Teams.](media/teams-phone-number.png)

No cliente Skype for Business, o número de telefone que você atribuir será listado na caixa **telefone comercial** e não poderá ser alterado por um usuário.
  
![Work Phone Number is Greyed Out.](media/5212fa64-b55c-4398-9709-a334f3ffa749.png)
  
> [!IMPORTANT]
> Se um usuário quiser [mudar seu número de telefone para o Skype for Business](https://support.office.com/article/20e03cc1-c023-4e5d-bafd-064ddb59ed5e) e o número de telefone no aplicativo Skype for Business não puder ser alterado ou estiver esmaecido, isso significará que um administrador o definiu para ele e ele não poderá ser alterado.
  


Ao configurar os usuários para que eles possam fazer e receber chamadas telefônicas, você deve primeiro usar o centro de administração do Skype for Business e atribuir um número de telefone, mas você pode alterar ou remover o número de telefone, se necessário.
  
Para saber como obter Planos de Chamadas no Office 365 e quanto custam, consulte [Licenças complementares do Skype for Business e Microsoft Teams](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).
  
> [!NOTE]
> One way to see whether a user has a license assigned is by going to **Skype for Business admin center** > **Voice** > **Voice users** and selecting the user. If a license is assigned, it will be noted under **Assigned license**. You also can use the Office 365 admin center. 
  
 ## <a name="assign-a-phone-number-to-a-user"></a>Atribuir um número de telefone a um usuário
 
![SFB-logo-30x30. png](media/sfb-logo-30x30.png) **usando o centro de administração do Skype for Business**
 
1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para o > **portal herdado** **do centro de administração do Microsoft Teams**.
    
3. Na navegação à esquerda, clique em**usuários de voz**de **voz** > .
   > [!NOTE]
   > Para ver a opção de **voz** no painel de navegação à esquerda no centro de administração do Skype for Business, primeiro você deve comprar pelo menos uma **licença do Enterprise E5**, uma licença complementar do **sistema de telefonia** ou uma licença do suplemento de conferência de **áudio** .
 
   
    
4. Na página **Usuários de voz**, localize e selecione o usuário ou usuários aos quais você quer atribuir um número de telefone.
    
5. No painel Ação, clique em **Atribuir número**.
    
6. Na página **atribuir número** , na lista **selecionar número para atribuir** , selecione o número de telefone do usuário.
    
    > [!TIP]
    > Se você não vir nenhum número de telefone listado, será necessário [obter números de telefone para os usuários](/microsoftteams/getting-phone-numbers-for-your-users) primeiro. Ou, se você usar o **centro de administração do Skype for Business** > **Voz** > página de**Números de telefone**, clique em **Adicionar**e depois em **Novos números de usuário**. 
  
7. Para atribuir ou alterar o endereço de emergência associado, em **Selecione um local de emergência validado**, selecione o local na lista ou, se você tiver muitos locais definidos, insira o nome da cidade na caixa de pesquisa e clique em **Pesquisar**.
    
8. Depois de escolher o número de telefone e o endereço de emergência, clique em **Salvar**.
    
    > [!NOTE]
    > Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for users to be enabled. If after 24 hours, if the phone number isn't assigned correctly, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b). We're here to help! 
  


 ## <a name="change-a-phone-number-for-a-user"></a>Alterar um número de telefone para um usuário
 
![SFB-logo-30x30. png](media/sfb-logo-30x30.png) **usando o centro de administração do Skype for Business**
 
1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para o > **portal herdado** **do centro de administração do Microsoft Teams**.
    
3. Na navegação à esquerda, clique em**usuários de voz**de **voz** > .
    
4. Na página **Usuários de voz**, localize e selecione o usuário ou usuários para os quais você quer alterar o número de telefone.
    
5. No painel Ação, em **número atribuído**, clique em **alterar**. 
    
6. Na página **Atribuir número**, clique em **Alterar número**.
    
7. Na página **Atribuir número**, em **Selecionar número para atribuir**, use a lista para selecionar o novo número de telefone do usuário. 
    
8. Para alterar o endereço de emergência associado, clique em **alterar local**e, em **Alterar endereço de emergência para**, selecione o local na lista ou, se você tiver muitos locais definidos, insira o nome da cidade na caixa de pesquisa e clique em **Pesquisa**.
    
9. Clique em **Salvar**.
    


 ## <a name="remove-a-phone-number-from-a-user"></a>Remover um número de telefone de um usuário
 
![SFB-logo-30x30. png](media/sfb-logo-30x30.png) **usando o centro de administração do Skype for Business**
 
1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para o > **portal herdado** **do centro de administração do Microsoft Teams**.
    
3. Na navegação à esquerda, clique em**usuários de voz**de **voz** > .
    
4. Na página **Usuários de voz**, localize e selecione o usuário ou usuários dos quais você quer remover o número de telefone.
    
5. No painel Ação, em **número atribuído**, clique em **remover**. 
    
6. Na página **Remover número atribuído selecionado?**, clique em **Sim**.
    

## <a name="related-topics"></a>Tópicos relacionados
[O que é validação de endereço?](/skypeforbusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[Gerenciar os números de telefone de sua organização](/microsoftteams/manage-phone-numbers-for-your-organization)

[Termos e condições das Chamadas de Emergência](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype for Business Online: etiqueta de aviso de isenção de responsabilidade por Chamadas de Emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 
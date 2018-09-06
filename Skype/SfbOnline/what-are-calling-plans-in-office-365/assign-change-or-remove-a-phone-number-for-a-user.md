---
title: Atribuir, alterar ou remover um número de telefone de um usuário
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 91089761-cb87-4119-885b-3713840dd9f7
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Calling Plans
description: Saiba como atribuir, alterar ou remover um número de telefone de trabalho para usuários do Skype for Business de modo que outras empresas e clientes possam ligar para eles.
ms.openlocfilehash: 8c80bf9da5471f1a7293a01ed9e2d56f6e1aa15b
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2018
ms.locfileid: "23780935"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user"></a>Atribuir, alterar ou remover um número de telefone de um usuário

Ao configurar Planos de Chamadas no Office 365, você atribui números de telefone para seus usuários. 

No cliente do Microsoft Teams, os números de telefone atribuídos podem ser visualizados clicando em **Chamadas**.

![Número de telefone do usuário exibido no Microsoft Teams.](../images/teams-phone-number.png)

No cliente do Skype for Business, o número de telefone que você atribuir será listado na caixa **Telefone Comercial** e não poderá ser alterado pelo usuário.
  
![O número de telefone comercial está em cinza.](../images/5212fa64-b55c-4398-9709-a334f3ffa749.png)
  
> [!IMPORTANT]
> Se um usuário desejar [alterar o número de telefone dele do Skype for Business](https://support.office.com/article/20e03cc1-c023-4e5d-bafd-064ddb59ed5e) e o número no aplicativo do Skype for Business não puder ser alterado ou estiver cinza, isso significa que ele foi configurado por um administrador e pode ser alterado.
  


Ao configurar usuários para fazer e receber chamadas telefônicas, você deve primeiro usar o centro de administração do Skype for Business para atribuir um número de telefone, mas ele pode ser alterado ou removido, se necessário.
  
Para saber como obter Planos de Chamadas no Office 365 e quanto custam, consulte [Licenças complementares do Skype for Business e Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
  
> [!NOTE]
> Uma maneira de verificar se um usuário tem uma licença atribuída é acessando o **centro de administração do Skype for Business** > **Voz** > **Usuários de voz** e selecionando o usuário. Se houver uma licença atribuída, ela estará listada sob **Licença atribuída**. Você também pode usar o centro de administração do Office 365. 
  
 ## <a name="assign-a-phone-number-to-a-user"></a>Atribuir um número de telefone a um usuário
 
![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Usar o centro de administração do Skype for Business**
 
1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Acesse o **centro de administração do Office 365** > **Centros de administração** > **Skype for Business**.
    
3. No painel de navegação esquerdo, clique em **Voz** > **Usuários de voz**.
   > [!NOTE]
 Para ver a opção **Voz** no painel de navegação à esquerda no centro de administração do Skype for Business, primeiro você deve comprar pelo menos uma **licença Enterprise E5**, uma licença complementar do **Sistema de Telefonia** ou de **Audioconferência**.
 
   
    
4. Na página **Usuários de voz**, localize e selecione o usuário ou usuários a quem deseja atribuir um número de telefone.
    
5. No Painel de ações, clique em **Atribuir número**.
    
6. Na página **Atribuir número**, na lista **Selecionar um número para atribuir**, selecione o número de telefone para o usuário.
    
    > [!TIP]
    > Se não houver nenhum número de telefone listado, você precisa [Obter números de telefone para seus usuários](getting-phone-numbers-for-your-users.md) primeiro. Ou, se você usar o **centro de administração do Skype for Business** > **Voz** > página de**Números de telefone**, clique em **Adicionar**e depois em **Novos números de usuário**. 
  
7. Para atribuir ou alterar o endereço de emergência associado, em **Selecionar a localização de emergência validada**, selecione a localização na lista ou, se você tiver muitas localizações definidas, insira o nome da cidade na caixa de pesquisa e clique em **Procurar**.
    
8. Depois de escolher o número de telefone e o endereço de emergência, clique em **Salvar**.
    
    > [!NOTE]
    > Devido à latência entre o Office 365 e o Skype for Business Online, pode levar até 24 horas para que os usuários sejam habilitados. Se, após 24 horas, o número do telefone não for atribuído corretamente, [entre em contato o suporte para produtos de empresas - Ajuda para Administradores](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b). Estamos aqui para ajudar! 
  


 ## <a name="change-a-phone-number-for-a-user"></a>Alterar um número de telefone de um usuário
 
![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Usar o centro de administração do Skype for Business**
 
1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Acesse o **centro de administração do Office 365** > **Centros de administração** > **Skype for Business**.
    
3. No painel de navegação esquerdo, clique em **Voz** > **Usuários de voz**.
    
4. Na página **Usuários de voz**, localize e selecione o usuário ou usuários para quem deseja alterar o número de telefone.
    
5. No Painel de ações em **Número atribuído**, clique em **Alterar**. 
    
6. Na página **Atribuir número**, clique em **Alterar número**.
    
7. Na página **Atribuir número**, em **Selecionar número para atribuir**, use a lista para selecionar o novo número de telefone do usuário. 
    
8. Para alterar o endereço de emergência associado, clique em **Alterar localização** e em **Alterar endereço de emergência** selecione a localização na lista ou, se você tiver muitas localizações definidas, insira o nome da cidade na caixa de pesquisa e clique em **Procurar**.
    
9. Clique em **Salvar**.
    


 ## <a name="remove-a-phone-number-from-a-user"></a>Remover um número de telefone de um usuário
 
![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Usar o centro de administração do Skype for Business**
 
1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Acesse o **centro de administração do Office 365** > **Centros de administração** > **Skype for Business**.
    
3. No painel de navegação esquerdo, clique em **Voz** > **Usuários de voz**.
    
4. Na página **Usuários de voz**, localize e selecione o usuário ou usuários de quem deseja remover o número de telefone.
    
5. No Painel de ações, em **Número atribuído**, clique em **Remover**. 
    
6. Na página **Remover número atribuído selecionado?**, clique em **Sim**.
    

## <a name="related-topics"></a>Tópicos relacionados
[O que é validação de endereço?](what-is-address-validation.md)

[Gerenciar os números de telefone de sua organização](/microsoftteams/manage-phone-numbers-for-your-organization)

[Termos e condições das Chamadas de Emergência](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype for Business Online: etiqueta de aviso de isenção de responsabilidade por Chamadas de Emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 
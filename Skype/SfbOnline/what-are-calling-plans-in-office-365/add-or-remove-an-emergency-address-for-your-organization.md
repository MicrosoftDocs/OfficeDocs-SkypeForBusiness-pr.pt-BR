---
title: Adicionar, alterar ou remover um endereço de emergência para sua organização
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: f954c67c-b73c-4473-b6cd-a0fbcd0fd4c9
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
description: 'Saiba como adicionar um endereço de emergência à sua conta do Skype for Business. '
ms.openlocfilehash: 5c22875873d2164c14d690523404481a514ef388
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34293731"
---
# <a name="add-change-or-remove-an-emergency-address-for-your-organization"></a>Adicionar, alterar ou remover um endereço de emergência para sua organização

Um endereço de emergência deve estar associado a um número de telefone, mas quando isso acontece, pode variar entre país/regiões. Por exemplo, nos Estados Unidos, você precisa associar um endereço de emergência quando atribui o número de telefone para o usuário. No Reino Unido, você precisa associar um endereço de emergência para o número de telefone quando você está obtendo os números de telefone do Office 365 ou transferindo números de telefone do seu provedor de serviço atual.
  
No matter which country/region you are in, it's possible to add a location or locations to an emergency address or remove an emergency address. Depending on the number of physical locations in your organization, you can create them for buildings, floors, and offices. See [What are emergency locations, addresses, and call routing?](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing) for some details.
  
Para saber como obter um Plano de Chamadas e quanto ele custa, consulte [Licenciamento de complemento para Skype for Business e Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
  
## <a name="add-an-emergency-address"></a>Adicionar um endereço de emergência

1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para o > **portal herdado**do **centro de administração do Microsoft Teams**.
    
3. No painel de navegação esquerdo, vá para **Voz** > **Locais de emergência** e, em seguida, clique no botão **Adicionar novo endereço**.
    
    > [!Important]
    > Para ver a opção de **voz** no painel de navegação à esquerda no centro de administração do Skype for Business, primeiro você deve comprar pelo menos uma **licença do Enterprise E5**, uma licença complementar do **sistema de telefonia** ou uma licença do suplemento de conferência de **áudio** .
    
4. No painel de Ações, em **Novo endereço**, digite as informações necessárias nas caixas.
    
5. Depois de inserir todas as informações do endereço, clique em **validar**.
    
    > [!IMPORTANT]
    > Validating a street or civic address involves making sure that it is legitimate and correctly formatted. It is possible that a partially correct emergency address, such as if you mistyped the name of the city, may still pass validation. Even though it's misspelled and passed validation, the combination of the misspelled name of city along with the other correct parts of the address are enough information to route the call to the appropriate emergency dispatch center. 
    
    > Observação: na Bélgica, na França, na Alemanha, na Irlanda, nos Países Baixos e na Espanha, é importante entender que, para ativar com êxito um número de telefone no Office 365, a configuração do endereço no local de emergência, que será usada para adquirir o número, deve corresponder ao código de área do número de telefone.
  
    Se o endereço não puder ser validado, você pode enviar uma solicitação de validação manual clicando em **Enviar uma solicitação de validação** se estiver tentando validar um endereço dos Estados Unidos, ou clique em **Abrir uma solicitação de serviço para obter ajuda com a validação de endereço** se você estiver fora dos Estados Unidos.
    
6. Depois que o endereço for validado, clique em **Salvar**.
    
## <a name="change-an-emergency-address"></a>Alterar um endereço de emergência

1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para o > **portal herdado**do **centro de administração do Microsoft Teams**.
    
3. No painel de navegação esquerdo, vá **** > para**locais de emergência de emergência**, selecione o endereço que você deseja alterar e, no painel Ação, clique em **Editar**.
    
    > [!IMPORTANT]
    > Para ver a opção de **voz** no painel de navegação à esquerda no centro de administração do Skype for Business, primeiro você deve comprar pelo menos uma **licença do Enterprise E5**, uma licença complementar do **sistema de telefonia** ou uma licença do suplemento de conferência de **áudio** .

4. Faça as alterações e, em seguida, clique em **validar**.

5. Clique em **Salvar**.

## <a name="remove-an-emergency-address"></a>Remover um endereço de emergência

1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para o > **portal herdado**do **centro de administração do Microsoft Teams**.
    
3. No painel de navegação esquerdo, vá **** > para**locais de emergência de emergência**, selecione o endereço que você deseja excluir e, no painel Ação, clique em **excluir**.
    
    > [!IMPORTANT]
    > Para ver a opção de **voz** no painel de navegação à esquerda no centro de administração do Skype for Business, primeiro você deve comprar pelo menos uma **licença do Enterprise E5**, uma licença complementar do **sistema de telefonia** ou uma licença do suplemento de conferência de **áudio** .

## <a name="troubleshooting"></a>Solução de problemas

**Número no estado "falha".**

Após adquirir um número do portal do Office 365, o status mudou de **"Provisioning"** para **"failed"**.

Geralmente, esse problema ocorre quando um número é adicionado do portal, usando um endereço de emergência apontando para um local que não corresponda ao código de área do telefone.

Para obter mais informações sobre o (s) número (s) que não foram ativados corretamente, execute o seguinte PowerShell:
 
> [! SYNTAX] Get-CsOnlineTelephoneNumber | Where-objeto {$ _. Activationstate-cnotcontains "ativado"} | FL

O resultado, além de outras informações, como region, ID e Activationstate, também devem conter o CityCode.

**Exemplo**, para um número Madri, o CityCode retornado será "EMEA-es-All-M_MA".

Se tiver sido usado um endereço de emergência errado, certifique-se de ter criado um novo endereço de emergência correspondente ao código de área do número e atribua-o ao número.

1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para o > **portal herdado**do **centro de administração do Microsoft Teams**.
    
3. No painel de navegação esquerdo, vá para**números de telefone**de **voz** > e clique duas vezes no número no estado **"falha"** e, no menu do site direito, selecione o **novo endereço de emergência**.


Observe que, após alterar o endereço de emergência, o status do número mudará para **"tarefa pendente"** e poderá levar até 24 horas para a ativação com êxito.

## <a name="related-topics"></a>Tópicos relacionados
[O que são locais e endereços de emergência e encaminhamento de chamadas?](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing)

[Gerenciar os números de telefone de sua organização](/microsoftteams/manage-phone-numbers-for-your-organization)

[Termos e condições das Chamadas de Emergência](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype for Business Online: etiqueta de aviso de isenção de responsabilidade por Chamadas de Emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 

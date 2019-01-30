---
title: Adicionar, alterar ou remover um endereço de emergência para sua organização
ms.author: tonysmit
author: tonysmit
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
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 'Learn how to add an emergency address to your Skype for Business account. '
ms.openlocfilehash: a1e1421e79b25da37f26c09b271abb67f7b3340b
ms.sourcegitcommit: 5cf9b45ad87aebfd46d3f1f757786c01804143ed
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/30/2019
ms.locfileid: "29635750"
---
# <a name="add-change-or-remove-an-emergency-address-for-your-organization"></a>Adicionar, alterar ou remover um endereço de emergência para sua organização

Um endereço de emergência deve ser associado um número de telefone, mas quando isso acontece pode variar entre países/regiões. Por exemplo, nos Estados Unidos, você precisa associar um endereço de emergência quando atribui o número de telefone para o usuário. No Reino Unido, você precisa associar um endereço de emergência para o número de telefone quando você está obtendo os números de telefone do Office 365 ou transferindo números de telefone do seu provedor de serviço atual.
  
Não importa qual em país/região você estiver, é possível adicionar um local ou mais locais a um endereço de emergência ou remover um endereço de emergência. Dependendo do número de locais físicos em sua organização, você pode criá-los para prédios, andares e escritórios. Consulte [Cite locais de emergência, endereços e roteamento de chamadas?](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing) para alguns detalhes.
  
Para saber como obter um Plano de Chamadas e quanto ele custa, consulte [Licenciamento de complemento para Skype for Business e Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
  
## <a name="add-an-emergency-address"></a>Adicionar um endereço de emergência

1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para as **equipes da Microsoft & Skype para Business Admin Center** > **portal herdada**.
    
3. No painel de navegação esquerdo, vá para **Voz** > **Locais de emergência** e, em seguida, clique no botão **Adicionar novo endereço**.
    
    > [!Important]
    > Para você ver a opção de **voz** no painel de navegação esquerdo no Skype para centro de administração de negócios, primeiro você deve comprar uma licença de complemento de **Conferência de áudio** , uma licença de complemento de **Sistema telefônico** ou pelo menos uma **licença Enterprise E5**.
    
4. No painel de Ações, em **Novo endereço**, digite as informações necessárias nas caixas.
    
5. Depois de digitar todas as informações do endereço, clique em **Validar**.
    
    > [!IMPORTANT]
    > [!IMPORTANTE] Validar um endereço cívico envolve certificar-se de que ele é legítimo e está formatado corretamente. É possível que um endereço de emergência parcialmente correto, tais como se você digitado incorretamente o nome da cidade, talvez ainda passar validação. Mesmo que tenha sido escrito errado e aprovado na validação, a combinação do nome errado da cidade com outras partes corretas do endereço é suficiente para encaminhar a chamada para o centro de despacho de emergência apropriado. 
    
    > Observação: Bélgica, França, Alemanha, Irlanda, países baixos e Espanha é importante entender que para ativar com êxito um número de telefone no Office 365 da configuração de endereço no local de emergência, que será usado para adquirir o número, devem coincidir com o código de área do número de telefone.
  
    Se o endereço não puder ser validado, você pode enviar uma solicitação de validação manual clicando em **Enviar uma solicitação de validação** se estiver tentando validar um endereço dos Estados Unidos, ou clique em **Abrir uma solicitação de serviço para obter ajuda com a validação de endereço** se você estiver fora dos Estados Unidos.
    
6. Depois que o endereço for validado, clique em **Salvar**.
    
## <a name="change-an-emergency-address"></a>Alterar um endereço de emergência

1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para as **equipes da Microsoft & Skype para Business Admin Center** > **portal herdada**.
    
3. No painel de navegação esquerdo, vá para **voz** > **locais de emergência**, selecione o endereço que você deseja alterar e, no painel de ações, clique em **Editar**.
    
    > [!IMPORTANT]
    > Para você ver a opção de **voz** no painel de navegação esquerdo no Skype para centro de administração de negócios, primeiro você deve comprar uma licença de complemento de **Conferência de áudio** , uma licença de complemento de **Sistema telefônico** ou pelo menos uma **licença Enterprise E5**.

4. Faça as alterações desejadas e clique em **Validar**.

5. Clique em **Salvar**.

## <a name="remove-an-emergency-address"></a>Remover um endereço de emergência

1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para as **equipes da Microsoft e Skype para Business Admin Center** > **portal herdada**.
    
3. No painel de navegação esquerdo, vá para **voz** > **locais de emergência**, selecione o endereço que você deseja excluir e, no painel de ações, clique em **Excluir**.
    
    > [!IMPORTANT]
    > Para você ver a opção de **voz** no painel de navegação esquerdo no Skype para centro de administração de negócios, primeiro você deve comprar uma licença de complemento de **Conferência de áudio** , uma licença de complemento de **Sistema telefônico** ou pelo menos uma **licença Enterprise E5**.

## <a name="troubleshooting"></a>Solução de problemas

**Número no estado "Falha".**

Após adquirir um número do portal do Office 365, o status será alterado de **"Provisionamento"** para **"Falha"**.

Geralmente, esse problema ocorre quando um número é adicionado a partir do portal, usando um endereço de emergência apontando para um local que não é compatível com o código de área do telefone.

Para obter mais informações sobre os números que não estava ativados corretamente, execute o Powershell a seguir:
 
> [! SINTAXE] Get-CsOnlineTelephoneNumber | Where-Object {$_. ActivationState - cnotcontains "Ativado"} | FL *

O resultado, reserve outras informações como região, id e ActivationState, também deve conter o CityCode.

O **exemplo**, para um número de Madri, o CityCode retornado será "EMEA-ES-ALL-M_MA".

Se, na verdade, um endereço de emergência errado tiver sido usado, verifique se você criou um novo endereço de emergência correspondente ao código de área do número e atribuí-lo ao número.

1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para as **equipes da Microsoft & Skype para Business Admin Center** > **portal herdada**.
    
3. No painel de navegação esquerdo, vá para **voz** > **Números de telefone**e, em seguida, clique duas vezes no número no estado **"Falha"** e, no menu site mão direita, selecione o **Novo endereço de emergência**.


Observe que após alterar o endereço de emergência, status do número será alterado para **"atribuição pendente"** e pode demorar até 24 horas para ativação com êxito.

## <a name="related-topics"></a>Tópicos relacionados
[O que são locais e endereços de emergência e encaminhamento de chamadas?](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing)

[Gerenciar os números de telefone de sua organização](/microsoftteams/manage-phone-numbers-for-your-organization)

[Termos e condições das Chamadas de Emergência](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype for Business Online: etiqueta de aviso de isenção de responsabilidade por Chamadas de Emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 

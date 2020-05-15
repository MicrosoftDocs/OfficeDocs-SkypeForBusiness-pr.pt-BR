---
title: Adicionar, alterar, remover locais de emergência
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
description: 'Saiba como adicionar, alterar ou remover um local de emergência para sua organização no centro de administração do Microsoft Teams. '
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 72730a326c6239b195d77f8a7bdde1b376da646f
ms.sourcegitcommit: 000515147632c6278bcda4505a1038014dda8e2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/14/2020
ms.locfileid: "44232482"
---
# <a name="add-change-or-remove-an-emergency-location-for-your-organization"></a>Adicionar, alterar ou remover um local de emergência para sua organização

Um local de emergência deve estar associado a um número de telefone, mas quando isso acontece, pode variar entre países e regiões. Por exemplo, nos Estados Unidos, você precisa associar uma localização de emergência ao atribuir o número de telefone ao usuário. No Reino Unido, você precisa associar um local de emergência ao número de telefone quando receber os números de telefone do Office 365 ou transferir números de telefone de seu provedor de serviços atual.

Não importa em que país ou região você está, você pode adicionar um local ou locais a um local de emergência e remover um local de emergência. Dependendo do número de locais físicos da sua organização, você pode criar locais para prédios, andares e escritórios. Consulte [gerenciar chamadas de emergência](what-are-emergency-locations-addresses-and-call-routing.md).
  
Para saber como obter um plano de chamadas e quanto eles custam, consulte [Licenciamento de Complementos do Microsoft Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

Você gerencia locais de emergência para sua organização no centro de administração do Microsoft Teams ou usando o PowerShell.
  
## <a name="add-an-emergency-location"></a>Adicionar um local de emergência

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

1. Na navegação à esquerda do centro de administração do Microsoft Teams, clique em **locais**  >  **endereços de emergência**.
2. Clique em **Adicionar local**.
3. Insira um nome e uma descrição para o local.
4. Selecione o país ou região e, em seguida, digite o endereço.

   > [!NOTE]
   > Na Bélgica, na França, na Alemanha, na Irlanda, Holanda e na Espanha, é importante entender que, para ativar com êxito um número de telefone no Office 365, o endereço configurado no local de emergência, que é usado para adquirir o número, deve corresponder ao código de área do número de telefone.
5. Se o endereço não for encontrado e você quiser editar manualmente o endereço, ative o desejo **Editar o formulário de endereço manualmente se não for possível encontrar o endereço selecionado**.
6. Clique em **Salvar**.

### <a name="using-powershell"></a>Usando o PowerShell

Veja [New-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/new-csonlineliscivicaddress).
    
## <a name="change-an-emergency-location"></a>Alterar um local de emergência

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

1. Na navegação à esquerda do centro de administração do Microsoft Teams, clique em **locais**  >  **endereços de emergência**.
2. Na lista, selecione o local que você deseja alterar e clique em **Editar**.
3. Faça as alterações desejadas.
4. Clique em **Salvar**.

> [!NOTE]
> Você pode alterar as informações de endereço para um local somente se o endereço não for validado. Se o endereço já estiver validado e você precisar alterar o endereço, exclua o local e, em seguida, crie um novo local com o endereço correto.

### <a name="using-powershell"></a>Usando o PowerShell

Consulte [set-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/set-csonlineliscivicaddress).
    
## <a name="remove-an-emergency-location"></a>Remover um local de emergência

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

1. Na navegação à esquerda do centro de administração do Microsoft Teams, clique em **locais**  >  **endereços de emergência**.
2. Na lista, selecione o local que você deseja remover e clique em **excluir**.

### <a name="using-powershell"></a>Usando o PowerShell

Consulte [Remove-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliscivicaddress).

## <a name="related-topics"></a>Tópicos relacionados

- [Gerenciar chamadas de emergência](what-are-emergency-locations-addresses-and-call-routing.md)
- [Adicionar, alterar ou remover um endereço de um local de emergência para sua organização](add-change-remove-emergency-place-organization.md)
- [Gerenciar os números de telefone de sua organização](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Termos e condições das Chamadas de Emergência](/microsoftteams/emergency-calling-terms-and-conditions)

---
title: O que são locais e endereços de emergência, e roteamento de chamada?
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 589bf5f5-490a-4215-8588-99bab7d33e31
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.locations.emergencyaddresses.overview
- ms.lync.lac.AddressAndLocation
ms.custom:
- Calling Plans
description: 'Saiba o que são locais de emergência, locais e encaminhamento de chamadas de emergência e como planejar e atribuí-los aos usuários. '
ms.openlocfilehash: ff29f807f0766889db8e6be4305e994bdc9637fe
ms.sourcegitcommit: d0f03b8abccdacb675f1063a7532397fd0e91a58
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/31/2019
ms.locfileid: "37901900"
---
# <a name="what-are-emergency-locations-places-and-call-routing"></a>O que são locais e endereços de emergência, e roteamento de chamada?

Ao configurar planos de chamada, você precisa atribuir um local de emergência para cada número de telefone ao adquirir o número de telefone ou ao atribuí-lo a um usuário para dar suporte a chamadas de emergência. Antes de poder atribuir um local de emergência a um número de telefone, você deve adicionar e validar um local de emergência. A validação verifica se o local de emergência é reconhecido e se está em um formato correto que pode ser usado por serviços de resposta de emergência. Se desejar, você pode adicionar um local no local de emergência para fornecer um local mais específico para o usuário. Por exemplo, o local pode ser um andar, um asa ou um escritório que está vinculado a um local de emergência específico. Embora locais de emergência sejam validados, os lugares não estão.
  
## <a name="what-are-emergency-locations"></a>O que são locais de emergência?

Um local de emergência é necessário para números de telefone ativos e quando ele é necessário depende do país/região. Nos Estados Unidos, é preciso um local de emergência quando um número é atribuído a um usuário. Para outros países, como na Europa, Oriente Médio e África (EMEA), é preciso um local de emergência quando você recebe o número de telefone do teams ou quando ele é transferido de outro provedor de serviços ou operadora para o Microsoft Teams.
  
Um local de emergência pode ser chamado de endereço cívico, endereço ou endereço físico com o lugar opcional. É o endereço residencial ou cívico de um local de negócios para sua organização. Por exemplo, o endereço *12345 residencial do Norte, Redmond, WA 98052* é usado para direcionar chamadas de emergência para as autoridades de expedição adequadas e para ajudar a localizar o chamador de emergência. É provável que você precise de mais de um local de emergência se a sua empresa tiver mais de um local corporativo físico.
  
Validar um endereço de emergência envolve certificar-se de que seja legítimo e formatado corretamente para serviços de resposta de emergência. É possível adicionar e salvar um local de emergência que não seja validado, mas somente locais validados podem ser associados a um usuário. Depois que um local de emergência for validado e salvo, você poderá atribuí-lo a um usuário. Para alterar um local de emergência salvo e validado, você precisará criar um novo.
  
## <a name="what-are-places"></a>O que são locais?

Um local está associado a um local de emergência para dar um local mais exato dentro de um edifício. Um local é geralmente um andar, um wingman de prédio ou um número de escritório onde o usuário está localizado. Você pode ter um número ilimitado de locais associados a um endereço de emergência.
  
Ao atribuir um local de emergência a um usuário, na verdade, é uma ID de localização referenciada quando você atribui o local. A ID de localização inclui o endereço de emergência referenciado (a rua ou o endereço cívico). Um local padrão está incluído em um local de emergência para casos em que os locais de construção não são necessários.
  
## <a name="what-is-emergency-call-routing"></a>O que é o encaminhamento de chamada de emergência?

Locais e locais de emergência são usados durante o processo de roteamento de chamadas de emergência para o centro de expedição apropriado ao distribuir os primeiros respondedores de emergência. Quando um usuário do teams disca um número de emergência, como a chamada é roteada para o serviço de resposta pública de segurança (PSAP) varia de acordo com o país e a região. Em alguns países, como os Estados Unidos e o Reino Unido, as chamadas são primeiro filtradas para determinar a localização atual do usuário antes de conectar a chamada ao centro de expedição apropriado. Em outros países e regiões, as chamadas são roteadas diretamente para o centro de expedição que serve o número de telefone associado ao chamador de emergência.
  
## <a name="create-add-and-assign-emergency-locations-and-places-to-your-users"></a>Criar, adicionar e atribuir locais e locais de emergência a seus usuários

1. **Planeje locais de emergência**. A primeira etapa é planejar seus locais de emergência. Liste todos os seus endereços físicos. Em seguida, com base em isso, determine se há necessidade de locais de emergência e, em caso afirmativo, quais são. Por exemplo, se uma empresa tem três prédios do escritório, cada um com quatro andares, é provável que haja três locais de emergência com o andares de um a quatro listado como um local para cada um.
    
2. **Adicione seus locais de emergência**. A próxima etapa é adicionar seus locais de emergência. Para saber mais, confira [Adicionar, alterar ou remover um local de emergência para sua organização](add-change-remove-emergency-location-organization.md).
    
    > [!IMPORTANT]
    > Validar um endereço ou um endereço cívico envolve garantir que seja legítimo e formatado corretamente. É possível que um endereço de emergência parcialmente correto, como um nome digitado incorretamente na cidade, ainda possa passar na validação. O processo de validação usa todas as partes de um determinado endereço para determinar se ele contém informações suficientes para direcionar a chamada para o centro de expedição de emergência apropriado. Em caso afirmativo, ele será retornado como validado e poderá ser atribuído a um número de telefone.
  
3. **Obter números de telefone**. A próxima etapa é obter números de telefone para seus usuários. Para isso, você pode receber novos números de telefone do Office 365 ou fazer a "portabilidade" ou transferência de números de telefone existentes para o Office 365. Para ver as etapas completas, consulte [transferir números de telefone para o Office 365](transfer-phone-numbers-to-office-365.md).
    
4. **Atribuir números de telefone**. A última etapa é habilitar os usuários a fazer e receber chamadas telefônicas. Para isso, é necessário atribuir um número de telefone a cada usuário. Consulte [atribuir, alterar ou remover um número de telefone para que um usuário](/microsoftteams/assign-change-or-remove-a-phone-number-for-a-user) atribua um número de telefone.

> [!NOTE]
> Se precisar de mais números de telefone do que isso, [entre em contato com o serviço de suporte PSTN](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md).

    
## <a name="related-topics"></a>Tópicos relacionados

[Diferentes tipos de números de telefone usados para Planos de Chamadas](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Termos e condições da chamada de emergência](emergency-calling-terms-and-conditions.md)
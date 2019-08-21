---
title: O que são locais de emergência, endereços e encaminhamento de chamadas?
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
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.locations.emergencyaddresses.overview
- ms.lync.lac.AddressAndLocation
ms.custom:
- Calling Plans
description: 'Learn what emergency address, location, and emergency call routing are, and how to plan and assign them to your users. '
ms.openlocfilehash: 979fab1cd099d568278efd61d06a3f8a75b04541
ms.sourcegitcommit: d4e69d46de564c445feb855cbee55954a7063bba
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/21/2019
ms.locfileid: "36483853"
---
# <a name="what-are-emergency-locations-addresses-and-call-routing"></a>O que são locais de emergência, endereços e encaminhamento de chamadas?

Quando você estiver configurando planos de chamada no Office 365, será preciso atribuir um endereço de emergência para cada número de telefone quando você receber o número de telefone ou atribuí-lo a um usuário para dar suporte à chamada de emergência. Antes de poder atribuir um endereço de emergência a um número de telefone, você deve criar e validar o endereço de emergência. A validação verifica se o endereço de emergência é reconhecido e se está em um formato correto que pode ser usado por serviços de resposta de emergência. Opcionalmente, você pode adicionar um local no endereço de emergência para fornecer um local mais específico para o usuário. Por exemplo, o local de emergência pode ser um andar, um asa ou um escritório que está vinculado a um endereço de emergência específico. Embora o endereço de emergência seja validado, os locais não são.
  
## <a name="what-are-emergency-addresses"></a>O que são endereços de emergência?

Um endereço de emergência é necessário para números de telefone ativos, mas quando necessário depende do país/região. Nos Estados Unidos, um endereço de emergência é necessário quando um número é atribuído a um usuário. Para outros países, como na Europa, Oriente Médio e África (EMEA), é preciso um endereço de emergência quando você recebe o número de telefone do Office 365 ou quando ele é transferido de outro provedor de serviços ou operadora.
  
Um endereço de emergência pode ser chamado de endereço cívico, endereço ou endereço físico. Trata-se da rua ou endereço cívico de um local de trabalho de sua empresa. Por exemplo, o endereço *12345 residencial do Norte, Redmond, WA 98052* é usado para direcionar chamadas de emergência para as autoridades de expedição adequadas e para ajudar a localizar o chamador de emergência. É provável que você precise de mais de um endereço de emergência caso sua empresa tenha mais de um local físico.
  
Validar um endereço de emergência envolve certificar-se de que seja legítimo e formatado corretamente para serviços de resposta de emergência. É possível criar e salvar um endereço de emergência que não seja validado, mas apenas endereços validados podem ser associados a um usuário. Quando o endereço de emergência for validado e salvo, ele pode ser atribuído a um usuário. Se você precisar alterar um endereço de emergência validado e salvo, deverá criar um novo.
  
## <a name="what-are-emergency-locations"></a>O que são locais de emergência?

Um local de emergência está associado a um endereço de emergência para dar um local mais exato dentro de um edifício. Um local de emergência pode ser o andar, ala do edifício ou número do escritório onde o usuário se encontra. Você pode ter um número ilimitado de locais associados a um endereço de emergência. 
  
Quando você atribui um endereço de emergência a um usuário, ele é, na verdade, uma ID de localização que é referenciada quando você atribui o endereço. A ID de localização inclui o endereço de emergência referenciado (a rua ou o endereço cívico). Um local de emergência padrão está incluído em um endereço de emergência para casos em que os locais de construção não são necessários. 
  
## <a name="what-is-emergency-call-routing"></a>O que é o encaminhamento de chamada de emergência?

Os endereços e locais de emergência são usados durante o processo de roteamento de chamadas de emergência para o centro de expedição apropriado durante a expedição de primeiros respondedores de emergência. Quando um usuário do Microsoft Teams ou do Skype for Business disca para um número de emergência, como a chamada é roteada para o serviço de resposta pública de segurança (PSAP), ele varia por país/região. Em alguns países, como os Estados Unidos e o Reino Unido, as chamadas serão reconectadas primeiro para determinar a localização atual do usuário antes de conectar a chamada ao centro de expedição apropriado. Em outros países/regiões, as chamadas serão roteadas diretamente para o centro de expedição, servindo ao número de telefone associado ao chamador de emergência.
  
## <a name="create-add-and-assign-emergency-locations-and-addresses-to-your-users"></a>Criar, adicionar e atribuir locais e endereços de emergência a seus usuários

1. **Planeje locais de emergência**. A primeira etapa é planejar seus locais de emergência. Você precisa listar todos os seus endereços físicos. Em seguida, com base nela, determine se os endereços de emergência são necessários e, em caso afirmativo, quais são os locais. Por exemplo, se uma empresa tiver 3 prédios da empresa com 4 andares, é provável que haja 3 endereços de emergência, com o andares 1-4 listado como um local para cada um deles.
    
2. **Crie e valide seus locais de emergência**. A próxima etapa é criar e validar seus endereços de emergência. Ao criar um endereço de emergência, é possível validá-lo. Para criar um endereço de emergência, consulte [Adicionar ou remover um endereço de emergência de sua organização](/SkypeForBusiness/what-are-calling-plans-in-office-365/add-or-remove-an-emergency-address-for-your-organization).
    
    > [!IMPORTANT]
    > [!IMPORTANTE] Validar um endereço cívico envolve certificar-se de que ele é legítimo e está formatado corretamente. É possível que um endereço de emergência parcialmente correto, como um nome digitado incorretamente na cidade, ainda possa passar na validação. O processo de validação usa todas as partes de um endereço para determinar se ele contém informações suficientes para encaminhar a chamada para o centro de despacho de emergência apropriado. Em caso afirmativo, ele será retornado como validado e poderá ser atribuído a um número de telefone. 
  
3. **Obter números de telefone**. A próxima etapa é obter números de telefone para seus usuários. Para isso, você pode receber novos números de telefone do Office 365 ou fazer a "portabilidade" ou transferência de números de telefone existentes para o Office 365. Para ver as etapas completas, consulte [transferir números de telefone para o Office 365](transfer-phone-numbers-to-office-365.md).
    
4. **Atribuir números de telefone**. A última etapa é habilitar os usuários a fazer e receber chamadas telefônicas. Para isso, é necessário atribuir um número de telefone a cada usuário. Consulte [atribuir, alterar ou remover um número de telefone para que um usuário](/microsoftteams/assign-change-or-remove-a-phone-number-for-a-user) atribua um número de telefone.

> [!NOTE]
> Se precisar de mais números de telefone, veja [Contatar o suporte de produtos para empresas - Ajuda para administradores](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

    
## <a name="related-topics"></a>Tópicos relacionados
[O que é validação de endereço?](/SkypeForBusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[Diferentes tipos de números de telefone utilizados para Planos de Chamadas](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Termos e condições para chamadas de emergência](emergency-calling-terms-and-conditions.md)

[Skype for Business Online: etiqueta de aviso de isenção de responsabilidade por Chamadas de Emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)


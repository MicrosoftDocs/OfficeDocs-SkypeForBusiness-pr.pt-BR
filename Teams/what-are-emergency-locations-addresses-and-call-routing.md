---
title: O que são locais e endereços de emergência e encaminhamento de chamadas?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 589bf5f5-490a-4215-8588-99bab7d33e31
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
f1keywords:
- ms.lync.lac.AddressAndLocation
ms.custom:
- Calling Plans
description: 'Learn what emergency address, location, and emergency call routing are, and how to plan and assign them to your users. '
ms.openlocfilehash: 469c31f7af2ef92bfa2f6a17939093a096e6d1d0
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2018
ms.locfileid: "23783034"
---
# <a name="what-are-emergency-locations-addresses-and-call-routing"></a>O que são locais e endereços de emergência e encaminhamento de chamadas?

Quando você estiver configurando o ato de chamar planos no Office 365, é necessário que um endereço de emergência ser atribuído a cada número de telefone quando você receber o número de telefone ou quando atribuído a um usuário para dar suporte a chamadas de emergência. Antes de atribuir um endereço de emergência para um número de telefone, um endereço de emergência deve ser criado e validado. A validação garante que o endereço de emergência seja reconhecido e se está em um formato correto que pode ser usado pelos serviços de resposta de emergência. Opcionalmente, um local dentro do endereço de emergência pode ser adicionado para oferecer um local mais específico para o usuário. Por exemplo, o local de emergência poderia ser um andar, borboleta ou temporária que está vinculada a um endereço específico de emergência. Embora o endereço de emergência são validados, não são locais.
  
## <a name="what-are-emergency-addresses"></a>O que são endereços de emergência?

Um endereço de emergência é necessário para números de telefone ativa, mas quando requerido é dependente de país/região. Nos Estados Unidos, um endereço de emergência é **necessário** quando um número é atribuído a um usuário. Para outros países, tais como na Europa, Oriente Médio e África (EMEA), um endereço de emergência é **necessária** quando você receber o número de telefone do Office 365 ou quando ele é transferido do outro provedor de serviços ou operadora.
  
Um endereço de emergência pode ser referido como um endereço residencial, endereço ou um endereço físico. Trata-se da rua ou endereço cívico de um local de trabalho de sua empresa. Por exemplo, o endereço *que 12345 Norte Main Street, Redmond, WA 98052* é usado para rotear chamadas de emergências para as autoridades apropriadas expedição e para ajudar a localizar o chamador de emergência. É provável que você precise de mais de um endereço de emergência caso sua empresa tenha mais de um local físico.
  
Validando um endereço de emergência envolve certificando-se de que ele é legítimo e formatada corretamente para serviços de resposta de emergência. É possível criar e salvar um endereço de emergência que não é validado, mas apenas endereços validados podem ser associados a um usuário. Quando o endereço de emergência for validado e salvo, ele pode ser atribuído a um usuário. Se você precisar alterar um endereço de emergência validado e salvo, deverá criar um novo.
  
## <a name="what-are-emergency-locations"></a>O que são locais de emergência?

Locais de emergência estão associados um endereço de emergência para fornecer um local mais exato dentro de um edifício. Um local de emergência pode ser o andar, ala do edifício ou número do escritório onde o usuário se encontra. Você pode ter um número ilimitado de locais associados a um endereço de emergência. 
  
Ao atribuir um endereço de emergência a um usuário, a ID do local é citada ao atribuir o endereço. A ID de localidade inclui o endereço de emergência referenciado (o endereço de rua ou residencial). Um local de emergência padrão está incluído em um endereço de emergência quando não for necessário fornecer a localização no edifício. 
  
## <a name="what-is-emergency-call-routing"></a>O que é o encaminhamento de chamada de emergência?

Locais e endereços de emergências são usados durante o processo de roteamento de chamadas de emergência para o Centro de expedição apropriada ao expedir emergências primeiros respondentes. Quando um Skype para o usuário de negócios disca um número de emergência, como a chamada é encaminhada para o operando PSAP atendimento público seguro ponto () irá variar por país/região. Em alguns países, como Estados Unidos e Reino Unido, as chamadas serão verificadas primeiro para determinar o local atual do usuário antes de se conectar a chamada para o Centro de expedição apropriada. Em outros países/regiões, as chamadas serão roteadas diretamente para o Centro de expedição servindo o número de telefone associado com o chamador de emergência.
  
## <a name="creating-adding-and-assigning-emergency-locations-and-addresses-to-your-users"></a>Criando, a adição e a atribuição de endereços e locais de emergência para seus usuários

1. **Planejar locais de emergência** A primeira etapa é planejar seus locais de emergências. Você precisa listar todos os seus endereços físicos. Em seguida, com base nisso, determine se locais para os endereços de emergências são necessários e, em caso afirmativo, quais são. Por exemplo, se uma empresa tiver 3 prédios cada com 4 andares, é provável que precise ser 3 endereços de emergências, com andares 1-4 listado como um local para cada um.
    
2. **Criar e validar seus locais de emergência** A próxima etapa é criar e validar seus endereços de emergência. Ao criar um endereço de emergência, é possível validá-lo. Para criar um endereço de emergência, consulte [Adicionar ou remover uma emergência de endereços para sua organização](/SkypeForBusiness/what-are-calling-plans-in-office-365/add-or-remove-an-emergency-address-for-your-organization).
    
    > [!IMPORTANT]
    > [!IMPORTANTE] Validar um endereço cívico envolve certificar-se de que ele é legítimo e está formatado corretamente. É possível que um endereço de emergência parcialmente correto, como um nome de cidade digitado incorretamente, passe na validação. O processo de validação usa todas as partes de um endereço para determinar se ele contém informações suficientes para encaminhar a chamada para o centro de despacho de emergência apropriado. Em caso afirmativo, ela será retornada como validado e, em seguida, pode ser atribuída a um número de telefone. 
  
3. **Obtenha números de telefone** A próxima etapa é obter os números de telefone para seus usuários. Para isso, você pode receber novos números de telefone do Office 365 ou fazer a "portabilidade" ou transferência de números de telefone existentes para o Office 365. Para ver as etapas completas, consulte [transferir os números de telefone para o Office 365](transfer-phone-numbers-to-office-365.md).
    
4. **Atribuir números de telefones** A última etapa é habilitar os usuários para fazerem e receberem ligações. Para isso, é necessário atribuir um número de telefone a cada usuário. Consulte [atribuir, alterar ou remover um número de telefone para um usuário](/SkypeForBusiness/what-are-calling-plans-in-office-365/assign-change-or-remove-a-phone-number-for-a-user) para atribuir um número de telefone.

> [!NOTE]
> Se precisar de mais números de telefone, veja [Contatar o suporte de produtos para empresas - Ajuda para administradores](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

    
## <a name="related-topics"></a>Tópicos relacionados
[O que é validação de endereço?](/SkypeForBusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[Diferentes tipos de números de telefone usados para Planos de Chamadas](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Termos e condições das Chamadas de Emergência](emergency-calling-terms-and-conditions.md)

[Skype for Business Online: etiqueta de aviso de isenção de responsabilidade por Chamadas de Emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)


---
title: "O que são locais e endereços de emergência e encaminhamento de chamadas?"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/17/2017
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- ms.lync.lac.AddressAndLocation
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: 589bf5f5-490a-4215-8588-99bab7d33e31
description: "Learn what emergency address, location, and emergency call routing are, and how to plan and assign them to your users. "
---

# O que são locais e endereços de emergência e encaminhamento de chamadas?

> [!IMPORTANT]
> Este artigo foi traduzido por um sistema de tradução automática, leia o aviso de isenção de responsabilidade.  
  
Quando você estiver configurando a chamar planos no Office 365, é necessário que um endereço de emergência ser atribuída a cada número de telefone quando você receber o número de telefone ou quando atribuído a um usuário para dar suporte a chamadas de emergência. Antes de atribuir um endereço de emergência para um número de telefone, um endereço de emergência deve ser criado e validado. A validação garante que o endereço de emergência é reconhecido e se está em um formato correto que pode ser usado pelos serviços de emergência resposta. Opcionalmente, um local dentro do endereço de emergência pode ser adicionado a fornecer um local mais específico para o usuário. Por exemplo, o local de emergência pode ser um andar, ala ou office que esteja vinculado a um endereço de emergência específico. Apesar de endereço de emergência são validados, locais não estão.
  
## O que são endereços de emergência?

Um endereço de emergência é necessário para números de telefone ativa, mas quando ele é necessário depende o país/região. Nos Estados Unidos, um endereço de emergência é **necessário** quando um número é atribuído a um usuário. Para outros países, como na Europa, Oriente Médio e África (EMEA), um endereço de emergência é **necessário** quando você recebe o número de telefone do Office 365 ou quando ele é transferido do outro provedor de serviços ou transportadora.
  
Um endereço de emergência pode ser denominado um endereço cívico, endereço ou um endereço físico. É o endereço físico ou cívico de um local de negócios para sua organização. Por exemplo, o endereço  *que 12345 Norte principal rua, Redmond, WA 98052*  é usado para rotear chamadas de emergência para as autoridades de distribuição apropriada e para ajudar a localizar o chamador de emergência. É provável que você precisará mais de um endereço de emergência se sua empresa tiver mais de um local de negócios física.
  
Validando um endereço de emergência envolve lembrando-se de que ele é legítima e formatado corretamente para serviços de emergência resposta. É possível criar e salvar um endereço de emergência que não for validado, mas apenas validados endereços podem estar associados a um usuário. Quando um endereço de emergência for validado e salvo, ele pode ser atribuído a um usuário. Se você precisar alterar um endereço de emergência validado salvo, você precisará criar um novo.
  
## O que são locais de emergência?

Locais de emergências estão associadas um endereço de emergência para dar um local exato mais dentro de um edifício. Um local de emergência costuma um andar, ala de construção ou número do office onde o usuário está localizado. Você pode ter um número ilimitado de locais associados a um endereço de emergência.
  
Ao atribuir um endereço de emergência a um usuário, a ID do local é citada ao atribuir o endereço. A ID do local inclui o endereço de emergência (a rua ou o endereço cívico). Um local de emergência padrão é incluído com um endereço de emergência quando não for necessário fornecer a localização no edifício. 
  
## O que é o encaminhamento de chamada de emergência?

Locais e endereços de emergências são usadas durante o processo de roteamento de chamadas de emergência para o Centro de distribuição apropriada ao expedir emergências respondentes primeiro. Quando um Skype para o usuário empresarial disca um número de emergência, como a chamada é roteada para o ponto de atendimento de segurança pública (PSAP) de fornecimento variam por país/região. Em alguns países, como os Estados Unidos e Reino Unido, as chamadas primeiro serão verificadas para determinar o local atual do usuário antes de se conectar a chamada para o Centro de distribuição apropriada. Em outros países/regiões, chamadas serão roteadas diretamente para o Centro de distribuição servir o número de telefone associado com o chamador de emergência.
  
## Criar, adicionar e atribuir locais de emergências e endereços aos seus usuários

1. **Planejar para locais de emergências** A primeira etapa é planejar seus locais de emergências. Você precisa listar todos os endereços físicos. Em seguida, com base no que, determinar se locais para os endereços de emergências são necessários e em caso afirmativo, quais eles são. Por exemplo, se uma empresa tem 3 office edifícios cada com 4 plantas, é provável que precise ser 3 endereços de emergências, com plantas listado como um local para cada 1-4.
    
2. **Criar e validar seus locais de emergência** A próxima etapa é criar e validar seus endereços de emergência. Ao criar um endereço de emergência, é possível validá-lo. Para criar um endereço de emergência, consulte[Adicionar ou remover um endereço de emergência para sua organização](add-or-remove-an-emergency-address-for-your-organization.md).
    
    > [!IMPORTANT]
    > Validar um endereço físico ou cívico envolve lembrando-se de que ele é legítima e formatado corretamente. É possível que um endereço de emergência parcialmente correto, como um nome de digitação da cidade, pode passar ainda pass validação. O processo de validação usa todas as partes de um determinado endereço para determinar se ela contém informações suficientes para rotear a chamada para o Centro de distribuição de emergência apropriado. Em caso afirmativo, ele será retornado como validados e, em seguida, pode ser atribuído a um número de telefone. 
  
3. **Obter números de telefone** A próxima etapa é obter números de telefone para seus usuários. Você pode fazer isso obtendo novos números de telefone do Office 365 ou por "portabilidade" ou transferir seus números de telefone existentes ao longo do Office 365. Para ver as etapas completas, consulte[Transferir números de telefone para o Office 365](transfer-phone-numbers-to-office-365.md).
    
4. **Atribuir números de telefone** A última etapa é permitir que usuários fazer e receber chamadas telefônicas. Para fazer isso, você deve atribuir um número de telefone para cada usuário. Consulte[Atribuir, alterar ou remover o número de telefone de um usuário](assign-change-or-remove-a-phone-number-for-a-user.md) para atribuir um número de telefone.
    
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Aviso de Isenção de Tradução Automática**: Este artigo foi traduzido por computador, sem intervenção humana. A Microsoft oferece essas traduções automáticas para ajudar as pessoas que não falam inglês a aproveitar os textos escritos sobre produtos, serviços e tecnologias da Microsoft. Como este artigo foi traduzido automaticamente, é possível que contenha erros de vocabulário, sintaxe ou gramática. 
  
## Consulte Também
<a name="MT_Footer"> </a>

#### 

[Skype for Business Online: emergência chamar rótulo de isenção de responsabilidade](https://go.microsoft.com/fwlink/?LinkID=692099)
  
[Termos e condições para chamadas de emergência](emergency-calling-terms-and-conditions.md)
  
[Áudio período discar complementar de conferência](../accessibility-and-regulatory/audio-conferencing-complimentary-dial-out-period.md)


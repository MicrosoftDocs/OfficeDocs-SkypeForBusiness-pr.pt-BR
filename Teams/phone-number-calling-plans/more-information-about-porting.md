---
title: Mais informações sobre portação
author: cichur
ms.author: v-mahoffman
manager: serdars
ms.reviewer: tonysmit,jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.voice.phonenumbers.porting.moreinfo
description: Receba as orientações que você precisa para por seus números de telefone para Microsoft Teams.
ms.openlocfilehash: 02023cc88fbab5b1063ed2734db500aa3c14aa9c
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60761749"
---
# <a name="more-information-about-porting"></a>Mais informações sobre portação

Aqui você encontrará mais informações sobre como portar seus números de telefone para Microsoft Teams.

Para obter instruções passo a passo completas, consulte [Transfer phone numbers to Teams](transfer-phone-numbers-to-teams.md).

Se precisar de ajuda ou se precisar obter mais números de telefone, entre em contato com a ajuda do [Service Desk TNS.](../manage-phone-numbers-for-your-organization/contact-tns-service-desk.md)

## <a name="port-order-account-information"></a>Informações da conta de pedido de portabilidade

Quando você estiver  na página Adicionar informações da conta do assistente de portabilidade para enviar um pedido de porta, você inserirá quase todas as mesmas informações que você forneceria na LOA, incluindo:
  
- Número da conta para o provedor de serviços ou operadora
    
- Número de telefone de cobrança (BTN)
    
- PIN - se necessário pelo provedor de serviços ou operadora atual
    
- Nome da organização
    
    > [!NOTE]
    > Isso aceitará apenas 25 caracteres, incluindo espaços. Se o nome da organização tiver mais de 25 caracteres, os primeiros 25 caracteres do nome serão enviados e a ordem de porta ainda será processada.
  
- Nome da pessoa autorizada a fazer alterações na conta
    
    > [!NOTE]
    > Isso aceitará apenas 15 caracteres, incluindo espaços. Se o nome da pessoa tiver mais de 15 caracteres, os 15 primeiros caracteres do nome serão enviados e o pedido de portabilidade ainda será processado. 
  
- Endereço do serviço
  
Para facilitar o envio da ordem de portabilidade e evitar erros, faça o seguinte:
  
- Remova todos os recursos (como Grupos de Busca) associados aos seus números. Certifique-se de que não haja recursos avançados de controle de chamadas, como a Busca de Chamadas ou Anel Distinto, habilitados nesses números de telefone.
    
- Verifique se você não fez novos pedidos de serviço ou se desconecta com seu provedor de serviços atual.
    
- Verifique se todos os números são da mesma operadora e da mesma conta.
    
- Verifique se as informações da conta que você forneceu correspondem exatamente às que a operadora de telefonia possui. Informações incompatibilidades são a causa mais comum de erros e podem atrasar sua ordem de porta.
    
> [!CAUTION]
> Não desconecte seus serviços com seu provedor de serviços ou operadora. Você deve manter seu serviço anterior ativo para por seus números de telefone para Teams. Não congele sua conta com seu provedor de serviços ou operadora. O congelamento da conta impede a alteração de operadoras nela. O usuário autorizado precisará enviar uma solicitação à operadora atual para cancelar o congelamento. Esse processo pode levar de uma a três semanas, dependendo da operadora.

## <a name="authorized-person-on-the-account"></a>Pessoa autorizada na conta

No assistente de portação, você deve inserir o nome da pessoa que está autorizada a fazer alterações na conta com o provedor de serviços ou operadora. O nome não é usado para processar a ordem de porta, mas é usado no caso de uma disputa ou se algo está incorreto quando os números são portados. Essa pessoa é responsável pela Carta de Autorização (LOA) para uma ordem de porta.
  
> [!NOTE]
> A caixa é limitada a 15 caracteres (incluindo espaços). Não ter o nome completo na caixa não atrasará ou cancelará a ordem de porta.
  
## <a name="whats-my-billing-telephone-number"></a>Qual é meu número de telefone de cobrança?

O número de telefone de cobrança (BTN) é o número de telefone principal incluído na sua conta e cobrado pelo provedor de serviços ou operadora. Se você estiver transferindo um número de telefone de uma conta que tenha apenas um número de telefone, você precisará inserir esse número de telefone. Se você estiver transferindo números de telefone de uma conta que tenha mais de um, você poderá olhar para sua conta ou entrar em contato com seu provedor de serviços ou operadora para determinar o que é o BTN para sua conta.

## <a name="what-should-i-put-in-for-the-account-number"></a>O que devo colocar para o número da conta?

Normalmente, você pode encontrar o número da conta em qualquer fatura ou fatura que você tenha do provedor de serviços ou da operadora, ou você pode fazer logoff no site da sua operadora. Se você ainda não sabe o número da conta, entre em contato com seu provedor de serviços ou operadora para obter.
  
> [!CAUTION]
>  É importante que você certifique-se de não usar espaços, traços ou hífens ao inserir seu provedor de serviços ou número de conta de operadora.

## <a name="what-should-i-put-in-for-the-organization-name"></a>O que devo colocar para o nome da organização?

Esse é o nome da sua organização. O nome da organização é limitado a 25 caracteres, o que inclui espaços. O nome da empresa não é usado para processar a solicitação de pedido de porta. Ele é usado no caso de uma disputa ou se algo está incorreto quando os números de telefone estão sendo portados. Se você não conseguir ajustar o nome inteiro da empresa na caixa, ele não atrasará ou cancelará a ordem de porta.
  
## <a name="what-should-i-put-in-for-the-service-address"></a>O que devo colocar para o endereço de serviço?

O endereço de serviço é diferente do endereço de cobrança ou de emergência que você registrou com seu provedor de serviços telefônicos ou operadora. Se você não sabe disso, entre em contato com seu provedor de serviços ou operadora para descobrir o endereço de serviço listado em sua conta.

## <a name="how-should-i-enter-the-phone-numbers"></a>Como inserir os números de telefone?
<a name="bkadding"> </a>

Ao enviar um pedido de porta, você deve usar um arquivo CSV formatado corretamente para enviar seus números de telefone. Aqui estão os requisitos para o arquivo CSV:

 - Você pode dar ao arquivo o nome que quiser.
 - O arquivo deve ter apenas uma coluna com um header chamado PhoneNumber.
 - Cada número de telefone deve estar em uma linha separada.
 - Telefone números podem ser dígitos somente ou no formato E.164.
 - O formato de número de telefone deve corresponder ao país ou região selecionado. Por exemplo, se você escolher o Reino Unido no assistente de portação, use 44, que é o código do país, seguido pelo número de telefone com o número correto de dígitos. Por exemplo, 4420812341234.

## <a name="how-do-i-see-the-status-of-my-port-order"></a>Como posso ver o status da minha ordem de porta?

Veja [Qual é o status dos pedidos de portabilidade?](port-order-status.md)

## <a name="related-topics"></a>Tópicos relacionados

- [O que é um pedido de portabilidade?](port-order-overview.md)
- [Diferentes tipos de números de telefone usados para Planos de Chamadas](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Gerenciar os números de telefone de sua organização](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [Termos e condições das Chamadas de Emergência](../emergency-calling-terms-and-conditions.md)
- [Rótulo de aviso de isenção de responsabilidade de chamada de emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

---
title: Mais informações sobre portabilidade
author: lanachin
ms.author: v-lanac
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
localization_priority: Normal
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
f1keyword: ms.teamsadmincenter.voice.phonenumbers.porting.moreinfo
description: Obtenha as diretrizes necessárias para portar seus números de telefone para o Microsoft Teams.
ms.openlocfilehash: 53a2c640a708e5da0ed4c0d30bb678fc3cd2cbe3
ms.sourcegitcommit: ced9b584eeceff7ca0109cba5823c7c3ddbd092e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/30/2019
ms.locfileid: "37886954"
---
# <a name="more-information-about-porting"></a>Mais informações sobre portabilidade

Aqui você encontrará mais informações sobre como fazer a portabilidade de seus números de telefone para o Microsoft Teams.

Para obter instruções passo a passo completas, consulte transferir números de telefone para o Microsoft Teams.

Se precisar de ajuda ou se precisar de mais números de telefone, entre em contato com a [ajuda da PSTN Desk do serviço](../manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md).

## <a name="port-order-account-information"></a>Informações da conta do pedido de portabilidade

Quando estiver na página **adicionar informações de conta** do assistente de portabilidade para enviar um pedido de portabilidade, você digitará quase todas as mesmas informações que você forneceria no loa, incluindo:
  
- Número da conta para o provedor de serviços ou operadora
    
- Número de telefone de cobrança (BTN)
    
- PIN-se necessário para o seu provedor de serviços ou operadora atual
    
- Nome da organização
    
    > [!NOTE]
    > Isso só aceita 25 caracteres, incluindo os espaços. Se o nome da organização tiver mais de 25 caracteres, serão enviados os 25 primeiros caracteres do nome e o pedido de portabilidade ainda será processado.
  
- Nome da pessoa autorizada a fazer alterações na conta
    
    > [!NOTE]
    > Isso só aceitará 15 caracteres, incluindo espaços. Se o nome da pessoa tiver mais de 15 caracteres, os 15 primeiros caracteres do nome serão enviados e o pedido de portabilidade ainda será processado. 
  
- Endereço do serviço
  
Para que o envio do pedido de portabilidade seja fácil e evitar erros, faça o seguinte:
  
- Remova todos os recursos (como grupos de buscas) associados a seus números. Certifique-se de que não haja recursos de controle de chamada avançados, como chamadas de caça ou toques distintos, habilitados nestes números de telefone.
    
- Certifique-se de que você não tenha feito nenhuma nova encomenda de serviço ou se desconectará com seu provedor de serviços atual.
    
- Verifique se todos os números são da mesma operadora e da mesma conta.
    
- Verifique se as informações da conta que você forneceu correspondem exatamente às que a operadora de telefonia possui. As informações incompatíveis são a causa mais comum de erros e podem atrasar seu pedido de portabilidade.
    
> [!CAUTION]
> Não desconecte seus serviços com o seu provedor de serviços ou operadora. Você deve manter o serviço anterior ativo para portar seus números de telefone para o Microsoft Teams. Não congele sua conta com seu provedor de serviços ou operadora. O congelamento da conta impede a alteração de operadoras nela. O usuário autorizado precisará enviar uma solicitação à operadora atual para cancelar o congelamento. Esse processo pode levar de uma a três semanas, dependendo da operadora.

## <a name="authorized-person-on-the-account"></a>Pessoa autorizada na conta

No assistente de portabilidade, você deve digitar o nome da pessoa que está autorizada a fazer alterações na conta com o provedor de serviços ou operadora. O nome não é usado para processar a ordem da portabilidade, mas é usado no caso de uma contestação, ou se algo estiver incorreto quando os números forem portados. Essa pessoa é responsável pela autorização da carta de autorização (LOA) para um pedido de portabilidade.
  
> [!NOTE]
> A caixa está limitada a 15 caracteres (incluindo espaços). Não ter o nome completo na caixa não atrasa ou cancela o pedido de portabilidade.
  
## <a name="whats-my-billing-telephone-number"></a>Qual é o meu número de telefone de cobrança?

O número de telefone de cobrança (BTN) é o número de telefone principal que está incluído em sua fatura e cobrado pelo seu provedor de serviços ou operadora. Se você estiver transferindo um número de telefone de uma conta que tem apenas um número de telefone, será necessário digitar este número de telefone. Se você estiver transferindo números de telefone de uma conta que tenha mais de um, examine sua fatura ou entre em contato com seu provedor de serviços ou operadora para determinar o que o BTN é para a sua conta.

## <a name="what-should-i-put-in-for-the-account-number"></a>O que devo colocar no número da conta?

Em geral, você pode encontrar o número da conta em qualquer cobrança ou fatura que você tiver do seu provedor de serviços ou operadora ou pode fazer logon no site da sua operadora. Se ainda não souber o número da conta, você pode entrar em contato com o provedor de serviços ou operadora para obtê-lo.
  
> [!CAUTION]
>  É importante que você não use espaços, traços ou hifens ao digitar seu provedor de serviço ou número de conta da operadora.

## <a name="what-should-i-put-in-for-the-organization-name"></a>O que devo colocar no nome da organização?

Este é o nome da sua organização. O nome da organização é limitado a 25 caracteres, que inclui espaços. O nome da empresa não é usado para processar a solicitação de pedido de portabilidade. Ele é usado no caso de uma contestação ou se algo estiver incorreto quando os números de telefone estiverem sendo portados. Se não for possível ajustar o nome inteiro da empresa na caixa, não será possível atrasar ou cancelar o pedido de portabilidade.
  
## <a name="what-should-i-put-in-for-the-service-address"></a>O que devo colocar no endereço do serviço?

O endereço do serviço é diferente do endereço de cobrança ou de emergência que você registrou com o seu provedor de serviços de telefonia ou operadora. Se você não souber isso, entre em contato com seu provedor de serviços ou operadora para saber qual é o endereço de serviço listado na sua conta.

## <a name="how-should-i-enter-the-phone-numbers"></a>Como devo inserir os números de telefone?
<a name="bkadding"> </a>

Ao enviar um pedido de portabilidade, você deve usar um arquivo CSV formatado corretamente para enviar seus números de telefone. Estes são os requisitos para o arquivo CSV:

 - Você pode fornecer o nome do arquivo desejado.
 - O arquivo só deve ter uma coluna com um cabeçalho chamado intervalo.
 - Cada número de telefone deve estar em uma linha separada.
 - Os números de telefone podem ser apenas dígitos ou no formato E. 164.
 - O formato do número de telefone deve corresponder ao país ou região selecionado. Por exemplo, se você escolher o Reino Unido no assistente de portabilidade, use 44, que é o código do país, seguido do número de telefone com o número correto de dígitos. Por exemplo, 4420812341234.

## <a name="how-do-i-see-the-status-of-my-port-order"></a>Como posso ver o status do meu pedido de portabilidade?

Veja qual é o status dos seus pedidos de portabilidade?

## <a name="related-topics"></a>Tópicos relacionados

- O que é um pedido de portabilidade?
- [Diferentes tipos de números de telefone usados para Planos de Chamadas](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Gerenciar os números de telefone de sua organização](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [Termos e condições das Chamadas de Emergência](../emergency-calling-terms-and-conditions.md)
- [Rótulo de isenção de isenção de emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

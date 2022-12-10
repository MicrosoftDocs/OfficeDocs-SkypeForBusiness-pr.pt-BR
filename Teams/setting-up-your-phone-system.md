---
title: Configurar o Sistema de telefonia da sua organização
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- m365solution-voice
- m365solution-scenario
- highpri
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-apr2020
- intro-get-started
description: Guia passo a passo detalhando como configurar o Sistema de Telefone do Teams para sua organização no Microsoft 365.
ms.openlocfilehash: 974cabac0d02f30d9371114e0f6886fdbc9f9389
ms.sourcegitcommit: feb9b7d10e38f5a629ee9202b5aaec5beef4de9b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2022
ms.locfileid: "69343171"
---
# <a name="set-up-phone-system-in-your-organization"></a>Configurar o Sistema de telefonia da sua organização

Este artigo fornece um roteiro para o conteúdo para a configuração da tecnologia do Phone System--Microsoft para habilitar o controle de chamada e os recursos do PBX (Private Branch Exchange) na nuvem Microsoft 365. Links para informações mais detalhadas estão disponíveis no final de cada etapa.

Antes de ler este artigo, certifique-se de ter lido [O que é sistema](what-is-phone-system-in-office-365.md) telefônico e [veja aqui o que você obtém com o Sistema de Telefone](here-s-what-you-get-with-phone-system.md). Os dois últimos artigos descrevem requisitos e recursos do Sistema Telefônico.

Este artigo descreve as seguintes etapas:

- [Etapa 1: comprar e atribuir uma licença do Sistema Telefônico](#step-1-buy-and-assign-a-phone-system-license)
- [Etapa 2: escolha uma opção de conectividade PSTN](#step-2-choose-a-pstn-connectivity-option)
- [Etapa 3: Obter números de telefone para seus usuários](#step-3-get-phone-numbers-for-your-users)
- [Etapa 4: Obter números de telefone para serviços](#step-4-get-phone-numbers-for-services-call-queues-auto-attendants)
- [Etapa 5: se você quiser configurar uma fila de chamadas](#step-5-if-you-want-to-set-up-a-call-queue)
- [Etapa 6: se você quiser configurar um atendente automático](#step-6-if-you-want-to-set-up-an-auto-attendant)
- [Etapa 7: Configurar créditos de comunicação para números gratuitos](#step-7-set-up-communications-credits-for-toll-free-numbers)

## <a name="step-1-buy-and-assign-a-phone-system-license"></a>Etapa 1: comprar e atribuir uma licença do Sistema Telefônico

Para atribuir uma licença do Sistema Telefônico a um único usuário, as etapas são as mesmas que atribuir uma licença Microsoft 365. Você também pode atribuir licenças a vários usuários em massa. Para obter mais informações sobre as licenças disponíveis do Sistema Telefônico e como adquirir e atribuir licenças, consulte [Licenças de complemento do Teams](/microsoftteams//teams-add-on-licensing/microsoft-teams-add-on-licensing) e [Atribuir licenças de complemento Microsoft Teams](/microsoftteams/teams-add-on-licensing/assign-teams-add-on-licenses).

## <a name="step-2-choose-a-pstn-connectivity-option"></a>Etapa 2. Escolha uma opção de conectividade PSTN

Para permitir que seus usuários façam e recebam chamadas externas, você precisará conectar o Sistema Telefônico à PSTN (Rede Telefônica Comutada Pública). Microsoft fornece várias opções para se conectar ao PSTN, incluindo:

- Chamando Plano. Uma solução all-in-the-cloud com Microsoft como sua operadora PSTN.

- Operator Connect. Se a operadora existente participar do programa Microsoft Operator Connect, ela poderá gerenciar a chamada PSTN e os SBCs (Controladores de Borda de Sessão) para você.

- Teams Phone Mobile. Se sua operadora existente participar do programa Telefonia móvel do Microsoft Teams, ela poderá gerenciar o serviço por usar números de telefone celular habilitados para SIM com o Teams.

- Roteamento direto. Use sua própria operadora PSTN conectando seus SBCs ao Sistema telefônico.

Para obter mais informações sobre todas as opções de conectividade, consulte [opções de conectividade PSTN](pstn-connectivity.md).

## <a name="step-3-get-phone-numbers-for-your-users"></a>Etapa 3: Obter números de telefone para seus usuários

Antes de configurar usuários em sua organização para fazer e receber chamadas telefônicas, você deve obter números de telefone para eles.

Para obter informações sobre como gerenciar números de telefone para seus usuários, confira os artigos a seguir. A forma como você gerencia números para um usuário depende da opção de conectividade PSTN escolhida.

- [Gerenciar números de telefone para sua organização](manage-phone-numbers-landing-page.md) – Fornece uma visão geral dos tipos de número de telefone com links para artigos específicos para adquirir e gerenciar números, dependendo da opção de conectividade PSTN.
Descreve os dois tipos de [números de telefone do usuário](manage-phone-numbers-landing-page.md#user-telephone-numbers).

- [Atribuir, alterar ou remover um número de telefone para um usuário](assign-change-or-remove-a-phone-number-for-a-user.md) – Descreve como atribuir e gerenciar os números de telefone adquiridos.

- [Quantos números de telefone você pode obter](how-many-phone-numbers-can-you-get.md) – descreve quantos números de telefone você pode obter, dependendo dos tipos de números de telefone e tipos de licenças que você comprou e atribuiu.

## <a name="step-4-get-phone-numbers-for-services-call-queues-auto-attendants"></a>Etapa 4: Obter números de telefone para serviços (filas de chamadas, atendentes automáticos)

Além de obter números de telefone para seus usuários, você pode adquirir números de telefone gratuitos ou de pedágio para serviços como atendentes automáticos e filas de chamadas. Um número de serviço pode lidar com centenas de chamadas simultaneamente, enquanto o número de telefone de um usuário só pode lidar com algumas chamadas simultaneamente.

Você pode obter números de serviço de Microsoft incluídos no licenciamento. Se você tiver conectividade PSTN por meio do Operator Connect ou do Direct Routing, poderá usar números de serviço fornecidos por sua própria operadora ou operador.

Para obter mais informações, confira:

- [Gerenciar números de telefone para sua organização](manage-phone-numbers-landing-page.md) – Fornece uma visão geral dos tipos de número de telefone com links para artigos específicos para adquirir e gerenciar números, dependendo da opção de conectividade PSTN.
Descreve [os números de telefone de serviço](manage-phone-numbers-landing-page.md#service-telephone-numbers) disponíveis de Microsoft incluídos no licenciamento. Para obter informações sobre números de serviço fornecidos pelo Operator Connect ou Pelo Roteamento Direto, entre em contato com seu provedor.

- [Quantos números de telefone você pode obter](how-many-phone-numbers-can-you-get.md) – descreve quantos números de telefone você pode obter, dependendo dos tipos de números de telefone e tipos de licenças que você comprou e atribuiu.

## <a name="step-5-if-you-want-to-set-up-a-call-queue"></a>Etapa 5: se você quiser configurar uma fila de chamadas

As filas de chamadas incluem saudações usadas quando alguém liga para um número de telefone para sua organização, a capacidade de colocar automaticamente as chamadas em espera e a capacidade de pesquisar o próximo agente de chamada disponível para lidar com a chamada. Você pode criar uma ou várias filas de chamadas para sua organização.

Para obter mais informações sobre filas de chamadas, consulte [Criar uma fila de chamadas](create-a-phone-system-call-queue.md).

## <a name="step-6-if-you-want-to-set-up-an-auto-attendant"></a>Etapa 6: se você quiser configurar um atendente automático

Os atendentes automáticos permitem que as pessoas que ligam para sua organização naveguem por um sistema de menus para levá-los para o departamento certo, chamar fila, pessoa ou operador.

Para obter informações sobre como configurar atendentes automáticos, consulte [Configurar um atendente automático](create-a-phone-system-auto-attendant.md).

## <a name="step-7-set-up-communications-credits-for-toll-free-numbers"></a>Etapa 7: Configurar créditos de comunicação para números gratuitos

Se você quiser usar números gratuitos com Microsoft Teams, precisará configurar créditos de comunicação. As chamadas gratuitas são cobradas por minuto e exigem um saldo positivo de Créditos de Comunicação.

Créditos de comunicação são uma maneira conveniente de adicionar números gratuitos para usar da seguinte maneira:

- Com números de serviço para aplicativos de voz, como atendentes automáticos ou filas de chamadas.

- Para discar qualquer número de telefone internacional quando você tiver assinaturas do Plano de Chamada Doméstica ou além do que está incluído em uma assinatura do Plano de Chamada Nacional e Internacional.

- Para discar e pagar por minuto depois de esgotar seu loteamento mensal.

- Para discar e pagar por minuto para todas as chamadas de saída, se você tiver um plano de chamada pago como você vai.

Para obter mais informações, consulte [O que são Créditos de Comunicação?](what-are-communications-credits.md) e [Configurar créditos de comunicação para sua organização](set-up-communications-credits-for-your-organization.md).

## <a name="related-articles"></a>Artigos relacionados

- [O que é o Sistema de Telefonia](what-is-phone-system-in-office-365.md)

- [Veja o que você obtém com o Sistema de Telefonia](here-s-what-you-get-with-phone-system.md)

- [Gerenciar números de telefone para sua organização](manage-phone-numbers-landing-page.md)

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
description: Guia passo a passo que detalha como configurar o Sistema de Telefonia do Teams para sua organização no Microsoft 365.
ms.openlocfilehash: beb82fd78fa58a4a3339dc1b7a5f54ceb5117479
ms.sourcegitcommit: 401cee68d4f6f9470d614dda12b9cb023f382ff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2022
ms.locfileid: "67999536"
---
# <a name="set-up-phone-system-in-your-organization"></a>Configurar o Sistema de telefonia da sua organização

Este artigo fornece um roteiro para o conteúdo para configurar o Sistema de Telefonia – tecnologia da Microsoft para habilitar o controle de chamadas e recursos de PBX (Private Branch Exchange) na nuvem do Microsoft 365. Links para informações mais detalhadas estão disponíveis no final de cada etapa.

Antes de ler este artigo, verifique se você leu o [](what-is-phone-system-in-office-365.md) que é o Sistema de Telefonia e veja o [que você obtém com o Sistema de Telefonia](here-s-what-you-get-with-phone-system.md). Os dois últimos artigos descrevem os requisitos e os recursos do Sistema de Telefonia.

Este artigo descreve as seguintes etapas:

- [Etapa 1: Comprar e atribuir uma licença do Sistema de Telefonia](#step-1-buy-and-assign-a-phone-system-license)
- [Etapa 2: Escolher uma opção de conectividade PSTN](#step-2-choose-a-pstn-connectivity-option)
- [Etapa 3: Obter números de telefone para seus usuários](#step-3-get-phone-numbers-for-your-users)
- [Etapa 4: Obter números de telefone para serviços](#step-4-get-phone-numbers-for-services-call-queues-auto-attendants)
- [Etapa 5: se você quiser configurar uma fila de chamadas](#step-5-if-you-want-to-set-up-a-call-queue)
- [Etapa 6: se você quiser configurar um atendedor automático](#step-6-if-you-want-to-set-up-an-auto-attendant)
- [Etapa 7: Configurar créditos de comunicação para números de chamada gratuita](#step-7-set-up-communications-credits-for-toll-free-numbers)

## <a name="step-1-buy-and-assign-a-phone-system-license"></a>Etapa 1: Comprar e atribuir uma licença do Sistema de Telefonia

Para atribuir uma licença do Sistema de Telefonia a um único usuário, as etapas são as mesmas que atribuir uma licença do Microsoft 365. Você também pode atribuir licenças a vários usuários em massa. Para obter mais informações sobre licenças disponíveis do Sistema de Telefonia e como adquirir e atribuir licenças, consulte licenças de complemento do Teams e atribuir [licenças](/microsoftteams//teams-add-on-licensing/microsoft-teams-add-on-licensing) de complemento do [Microsoft Teams](/microsoftteams/teams-add-on-licensing/assign-teams-add-on-licenses).

## <a name="step-2-choose-a-pstn-connectivity-option"></a>Etapa 2. Escolher uma opção de conectividade PSTN

Para permitir que os usuários façam e recebam chamadas externas, você precisará conectar o Sistema de Telefonia à Rede Telefônica Pública Comunada (PSTN). A Microsoft fornece várias opções para se conectar ao PSTN, incluindo:

- Plano de chamada. Uma solução totalmente na nuvem com a Microsoft como sua operadora PSTN.

- Conexão do operador. Se sua operadora existente participar do programa Microsoft Operator Connect, ela poderá gerenciar chamadas PSTN e SBCs (Controladores de Borda de Sessão) para você.

- Roteamento Direto. Use sua própria operadora PSTN conectando seus SBCs ao Sistema de Telefonia.

Para obter mais informações sobre todas as opções de conectividade, consulte [as opções de conectividade PSTN](pstn-connectivity.md).

## <a name="step-3-get-phone-numbers-for-your-users"></a>Etapa 3: Obter números de telefone para seus usuários

Antes de configurar usuários em sua organização para fazer e receber chamadas telefônicas, você deve obter números de telefone para eles.

Para obter informações sobre como gerenciar números de telefone para seus usuários, consulte os artigos a seguir. A maneira como você gerencia números para um usuário depende da opção de conectividade PSTN escolhida.

- [Gerenciar números de telefone para](manage-phone-numbers-landing-page.md) sua organização – fornece uma visão geral dos tipos de número de telefone com links para artigos específicos para adquirir e gerenciar números, dependendo da opção de conectividade PSTN.
Descreve os dois tipos de números [de telefone de usuário](manage-phone-numbers-landing-page.md#user-telephone-numbers).

- [Atribuir, alterar ou remover um número de](assign-change-or-remove-a-phone-number-for-a-user.md) telefone para um usuário – Descreve como atribuir e gerenciar os números de telefone que você adquiriu.

- [Quantos números de](how-many-phone-numbers-can-you-get.md) telefone você pode obter – Descreve quantos números de telefone você pode obter, dependendo dos tipos de números de telefone e tipos de licenças que você comprou e atribuiu.

## <a name="step-4-get-phone-numbers-for-services-call-queues-auto-attendants"></a>Etapa 4: Obter números de telefone para serviços (filas de chamadas, atendedores automáticos)

Além de obter números de telefone para seus usuários, você pode adquirir números de chamada tarifada ou gratuita para serviços como atendedores automáticos e filas de chamadas. Um número de serviço pode lidar com centenas de chamadas simultaneamente, enquanto o número de telefone de um usuário só pode lidar com algumas chamadas simultaneamente.

Você pode obter números de serviço da Microsoft que estão incluídos em seu licenciamento. Se você tiver conectividade PSTN por meio do Operator Connect ou do Roteamento Direto, poderá usar números de serviço fornecidos por sua própria operadora ou operador.

Para obter mais informações, consulte:

- [Gerenciar números de telefone para](manage-phone-numbers-landing-page.md) sua organização – fornece uma visão geral dos tipos de número de telefone com links para artigos específicos para adquirir e gerenciar números, dependendo da opção de conectividade PSTN.
Descreve os [números de telefone de](manage-phone-numbers-landing-page.md#service-telephone-numbers) serviço disponíveis na Microsoft que estão incluídos em seu licenciamento. Para obter informações sobre números de serviço fornecidos pelo Operator Connect ou pelo Roteamento Direto, entre em contato com seu provedor.

- [Quantos números de](how-many-phone-numbers-can-you-get.md) telefone você pode obter – Descreve quantos números de telefone você pode obter, dependendo dos tipos de números de telefone e tipos de licenças que você comprou e atribuiu.

## <a name="step-5-if-you-want-to-set-up-a-call-queue"></a>Etapa 5: se você quiser configurar uma fila de chamadas

As filas de chamadas incluem saudações que são usadas quando alguém liga para um número de telefone para sua organização, a capacidade de colocar automaticamente as chamadas em espera e a capacidade de pesquisar o próximo agente de chamada disponível para lidar com a chamada. Você pode criar uma ou várias filas de chamadas para sua organização.

Para obter mais informações sobre filas de chamadas, [consulte Criar uma fila de chamadas](create-a-phone-system-call-queue.md).

## <a name="step-6-if-you-want-to-set-up-an-auto-attendant"></a>Etapa 6: se você quiser configurar um atendedor automático

Os atendedores automáticos permitem que as pessoas que chamam sua organização naveguem por um sistema de menus para obtê-los para o departamento certo, fila de chamadas, pessoa ou operador.

Para obter informações sobre como configurar atendedores automáticos, consulte [Configurar um atendedor automático](create-a-phone-system-auto-attendant.md).

## <a name="step-7-set-up-communications-credits-for-toll-free-numbers"></a>Etapa 7: Configurar Créditos de Comunicação para números de chamada gratuita

Se você quiser usar números de chamada gratuita com o Microsoft Teams, precisará configurar créditos de comunicação. As chamadas gratuitas são cobradas por minuto e exigem um saldo positivo de Créditos de Comunicação.

Os Créditos de Comunicação são uma maneira conveniente de adicionar números de chamada gratuita a serem usados da seguinte maneira:

- Com números de serviço para aplicativos de voz, como atendedores automáticos ou filas de chamadas.

- Para discar qualquer número de telefone internacional quando você tiver assinaturas do Plano de Chamadas Domésticas ou além do que está incluído em uma assinatura do Plano de Chamadas Domésticas e Internacionais.

- Para discar e pagar por minuto depois de esgotar sua atribuição de minuto mensal.

- Para discar e pagar por minuto por todas as chamadas de saída, se você tiver um Plano de Chamadas Pago Conforme o Uso.

Para obter mais informações, consulte [O que são Créditos de Comunicação?](what-are-communications-credits.md) e [Configurar Créditos de Comunicação para sua organização](set-up-communications-credits-for-your-organization.md).

## <a name="related-articles"></a>Artigos relacionados

- [O que é o Sistema de Telefonia](what-is-phone-system-in-office-365.md)

- [Veja o que você obtém com o Sistema de Telefonia](here-s-what-you-get-with-phone-system.md)

- [Gerenciar números de telefone para sua organização](manage-phone-numbers-landing-page.md)

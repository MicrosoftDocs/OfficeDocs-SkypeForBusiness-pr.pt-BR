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
description: Guia passo a passo detalhando como configurar o Teams Sistema de Telefonia para sua organização em Microsoft 365.
ms.openlocfilehash: 3a5c275c7d7d881ff770e6e84a3d4fa935d2827f
ms.sourcegitcommit: 71edff2670367082312de59c4e21775682871418
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/01/2022
ms.locfileid: "63043339"
---
# <a name="set-up-phone-system-in-your-organization"></a>Configurar o Sistema de telefonia da sua organização

Este artigo fornece um roteiro para o conteúdo para Sistema de Telefonia configuração da tecnologia da Microsoft para habilenciar o controle de chamada e recursos de PBX (Private Branch Exchange) na nuvem Microsoft 365 privada. Links para informações mais detalhadas estão disponíveis no final de cada etapa. 

Antes de ler este artigo, leia [What is Sistema de Telefonia](what-is-phone-system-in-office-365.md) [and Here's what you get with Sistema de Telefonia](here-s-what-you-get-with-phone-system.md). Os dois últimos artigos descrevem Sistema de Telefonia e recursos.    

Este artigo descreve as seguintes etapas: 

- [Etapa 1: comprar e atribuir uma Sistema de Telefonia de usuário](#step-1-buy-and-assign-a-phone-system-license)  
- [Etapa 2: Escolher uma opção de conectividade PSTN](#step-2-choose-a-pstn-connectivity-option) 
- [Etapa 3: Obter números de telefone para seus usuários](#step-3-get-phone-numbers-for-your-users)
- [Etapa 4: Obter números de telefone para serviços](#step-4-get-phone-numbers-for-services-call-queues-auto-attendants)
- [Etapa 5: se você deseja configurar uma fila de chamada](#step-5-if-you-want-to-set-up-a-call-queue) 
- [Etapa 6: se você deseja configurar um atendimento automático](#step-6-if-you-want-to-set-up-an-auto-attendant) 
- [Etapa 7: Configurar créditos de comunicação para números gratuitos](#step-7-set-up-communications-credits-for-toll-free-numbers)
 

## <a name="step-1-buy-and-assign-a-phone-system-license"></a>Etapa 1: comprar e atribuir uma Sistema de Telefonia de usuário

Para atribuir uma Sistema de Telefonia a um único usuário, as etapas são as mesmas que atribuir uma Microsoft 365 de usuário. Você também pode atribuir licenças a vários usuários em massa. Para obter mais informações sobre Sistema de Telefonia licenças de Sistema de Telefonia disponíveis e como adquirir e atribuir licenças, consulte  [Teams licenças](/microsoftteams//teams-add-on-licensing/microsoft-teams-add-on-licensing) de complemento e [Atribuir licenças de complemento Teams Microsot](/microsoftteams/teams-add-on-licensing/assign-teams-add-on-licenses).

## <a name="step-2-choose-a-pstn-connectivity-option"></a>Etapa 2. Escolha uma opção de conectividade PSTN 
 
Para permitir que os usuários façam e recebam chamadas externas, você precisará se conectar Sistema de Telefonia rede telefônica pública comutado (PSTN). A Microsoft fornece várias opções para se conectar ao PSTN, incluindo: 

- Plano de Chamada. Uma solução completa na nuvem com a Microsoft como operadora PSTN. 

- Operador Conexão. Se sua operadora existente participar do programa de Conexão microsoft operator, eles poderão gerenciar as chamada PSTN e os Controladores de Borda de Sessão (SBCs) para você. 

- Roteamento Direto. Use sua própria operadora PSTN conectando seus SBCs a Sistema de Telefonia. 

Para obter mais informações sobre todas as opções de conectividade, consulte [Opções de conectividade PSTN](pstn-connectivity.md).   

## <a name="step-3-get-phone-numbers-for-your-users"></a>Etapa 3: Obter números de telefone para seus usuários

Antes de configurar usuários em sua organização para fazer e receber chamadas telefônicas, você deve obter números de telefone para eles.

Para obter informações sobre como gerenciar números de telefone para seus usuários, consulte os artigos a seguir. A forma como você gerencia números para um usuário depende da opção de conectividade PSTN escolhida.   

- [Gerenciar números de telefone para sua](manage-phone-numbers-landing-page.md) organização – fornece uma visão geral dos tipos de número de telefone com links para artigos específicos para adquirir e gerenciar números, dependendo da opção de conectividade PSTN. Descreve os dois tipos de números [de telefone do usuário](manage-phone-numbers-landing-page.md#user-telephone-numbers). 
 
- [Atribuir, alterar ou remover um número de](assign-change-or-remove-a-phone-number-for-a-user.md) telefone para um usuário – descreve como atribuir e gerenciar os números de telefone adquiridos. 
 
- [Quantos números de](how-many-phone-numbers-can-you-get.md) telefone você pode obter – descreve quantos números de telefone você pode obter dependendo dos tipos de números de telefone e tipos de licenças que você comprou e atribuiu. 


## <a name="step-4-get-phone-numbers-for-services-call-queues-auto-attendants"></a>Etapa 4: Obter números de telefone para serviços (filas de chamada, atendimento automático)

Além de obter números de telefone para seus usuários, você pode adquirir números de telefone gratuitos ou de chamada gratuita para serviços como atendimento automático e filas de chamadas. Um número de serviço pode manipular centenas de chamadas simultaneamente, enquanto o número de telefone de um usuário só pode manipular algumas chamadas simultaneamente.   

Você pode obter números de serviço da Microsoft incluídos em seu licenciamento. Se você tiver conectividade PSTN por meio de operador Conexão ou Roteamento Direto, poderá usar números de serviço fornecidos por sua própria operadora ou operador. 

Para obter mais informações, consulte:

- [Gerenciar números de telefone para sua](manage-phone-numbers-landing-page.md) organização – fornece uma visão geral dos tipos de número de telefone com links para artigos específicos para adquirir e gerenciar números, dependendo da opção de conectividade PSTN.  
Descreve os [números de telefone de serviço](manage-phone-numbers-landing-page.md#service-telephone-numbers) disponíveis da Microsoft que estão incluídos em seu licenciamento. Para obter informações sobre números de serviço fornecidos pelo Operador Conexão ou Roteamento Direto, entre em contato com seu provedor. 

- [Quantos números de](how-many-phone-numbers-can-you-get.md) telefone você pode obter – descreve quantos números de telefone você pode obter dependendo dos tipos de números de telefone e tipos de licenças que você comprou e atribuiu. 

## <a name="step-5-if-you-want-to-set-up-a-call-queue"></a>Etapa 5: se você deseja configurar uma fila de chamada

As filas de chamadas incluem saudações usadas quando alguém liga para um número de telefone para sua organização, a capacidade de colocar automaticamente as chamadas em espera e a capacidade de procurar o próximo agente de chamada disponível para lidar com a chamada. Você pode criar uma ou várias filas de chamadas para sua organização. 

Para obter mais informações sobre filas de chamada, consulte [Create a call queue](create-a-phone-system-call-queue.md).

## <a name="step-6-if-you-want-to-set-up-an-auto-attendant"></a>Etapa 6: se você deseja configurar um atendimento automático

Os atendentes automáticos permitem que as pessoas que ligarem para sua organização naveguem por um sistema de menus para que eles acessem o departamento certo, fila de chamada, pessoa ou operador.  

Para obter informações sobre como configurar os atendimentos automáticos,  [consulteSet up a auto attendant](create-a-phone-system-auto-attendant.md).

## <a name="step-7-set-up-communications-credits-for-toll-free-numbers"></a>Etapa 7: Configurar Créditos de Comunicações para números gratuitos

Se você quiser usar números gratuitos com Microsoft Teams, será necessário configurar créditos de comunicação. As chamadas gratuitas são cobradas por minuto e exigem um saldo positivo de Créditos de Comunicações. 

Os Créditos de Comunicações são uma maneira conveniente de adicionar números gratuitos a ser usado da seguinte maneira: 

- Com números de serviço para aplicativos de voz, como atendimento automático ou filas de chamadas. 

- Para discar qualquer número de telefone internacional quando você tiver assinaturas do Plano de Chamadas Domésticas ou além do que está incluído em uma assinatura do Plano de Chamadas Domésticas e Internacionais. 

- Para discar e pagar por minuto depois de esgotar sua loteação mensal. 

Para obter mais informações, consulte  [O que são Créditos de Comunicação?](what-are-communications-credits.md) [e Configurar Créditos de Comunicação para sua organização](set-up-communications-credits-for-your-organization.md).
  

## <a name="related-topics"></a>Tópicos relacionados

- [O que é o Sistema de Telefonia](what-is-phone-system-in-office-365.md)

- [Veja o que você obtém com o Sistema de Telefonia](here-s-what-you-get-with-phone-system.md)

- [Gerenciar números de telefone para sua organização](manage-phone-numbers-landing-page.md)


    
  
 

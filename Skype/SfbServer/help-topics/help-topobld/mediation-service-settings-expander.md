---
title: Expansor de Configurações de Serviço de Mediação
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FeMediationServiceSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 142c1acd-cdaa-4922-8379-aa1bdf56a964
description: 'Em Servidor de Mediação, você pode especificar o seguinte:'
ms.openlocfilehash: 4535698552b918c57a8c76741ffaaef2c1b66b48
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23253792"
---
# <a name="mediation-service-settings-expander"></a>Expansor de Configurações de Serviço de Mediação

Em **Servidor de Mediação**, você pode especificar o seguinte:

Se você estiver colocando o servidor de mediação para o pool de Front-End ou servidor Standard Edition, marque a caixa de seleção **servidor de mediação posicionado habilitado**. Se você escolher não coloque o servidor de mediação, não há nenhuma configuração definíveis nesta seção.

Se você tiver habilitado a colocação do servidor de mediação, você precisará definir o intervalo de portas de escuta do servidor para a segurança de camada de transporte (TLS). Por padrão, essa porta é a 5067. Se você selecionar **Habilitar porta TCP**, será necessário definir uma porta TCP para o Servidor de Mediação colocado. Essa é uma configuração opcional e você deve consultar os requisitos de seu gateway ou os requisitos de sua PSTN (Rede Telefônica Pública Comutada) a fim de determinar se precisa disso. Por padrão, o valor de porta TCP é 5068.

Você define os gateways PSTN associados com o servidor de mediação colocado. Se você já tenha definido gateways, eles estarão disponíveis para associar o servidor de mediação.

Se você tiver mais de um gateway associado a um servidor de mediação, o primeiro gateway associado será o gateway padrão. Se precisar escolher outro gateway como o gateway padrão, selecione o gateway que você deseja tornar padrão e clique em **Tornar Padrão**. Para desmarcar o gateway como padrão, clique em **Desfazer Padrão**.

Para obter detalhes sobre como definir e configurar as definições para o pool de Front End do Enterprise Edition ou servidor Standard Edition, consulte [Defining and Configuring the Topology](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) e [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).



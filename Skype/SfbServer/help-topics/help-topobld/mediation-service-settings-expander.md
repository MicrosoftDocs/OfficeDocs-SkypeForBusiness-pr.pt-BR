---
title: Expansor de Configurações de Serviço de Mediação
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FeMediationServiceSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 142c1acd-cdaa-4922-8379-aa1bdf56a964
description: 'Para o  Servidor de Mediação, você pode especificar:'
ms.openlocfilehash: 60312afc4ab487be474eeef6a8432e3522058275
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104417"
---
# <a name="mediation-service-settings-expander"></a>Expansor de Configurações de Serviço de Mediação

Para o  **Servidor de Mediação**, você pode especificar:

Se você estiver posicionada o Servidor de Mediação no pool de Front-End ou no servidor Standard Edition, marque a caixa de seleção Servidor de Mediação **Alocado habilitado**. Se você escolher não posicionar o Servidor de Mediação, não haverá configurações para definição nesta seção.

Se você tiver habilitado o posicionamento do Servidor de Mediação, será necessário definir o intervalo de porta de escuta no servidor para Transport Layer Security (TLS). Por padrão, essa porta é 5067. Se você selecionar **Habilitar porta TCP**, será necessário definir uma porta TCP (Transmission Control Protocol) para o Servidor de Mediação colocado. Essa é uma configuração opcional e você deve consultar os requisitos de seu gateway ou os requisitos de sua PSTN (Rede Telefônica Pública Comutada) a fim de determinar se precisa disso. Por padrão, o valor de porta TCP é 5068.

Defina os gateways PSTN associados ao Servidor de Mediação posicionado. Se você já tiver definido os gateways, eles estarão disponíveis para associação com o Servidor de Mediação.

Se houver mais de um gateway associado ao Servidor de Mediação, o primeiro gateway associado será o gateway padrão. Se você precisar escolher outro gateway como o gateway padrão, selecione o gateway que você deseja tornar padrão e clique em **Tornar Padrão**. Para desmarcar o gateway como padrão, clique em **Desfazer Padrão**.

Para obter detalhes sobre como definir e configurar as configurações para o pool de front-end enterprise edition ou servidor Standard Edition, consulte Defining and [Configuring the Topology](/previous-versions/office/lync-server-2013/lync-server-2013-defining-and-configuring-the-topology) and [Deploying Mediation Servers and Defining Peers](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mediation-servers-and-defining-peers).
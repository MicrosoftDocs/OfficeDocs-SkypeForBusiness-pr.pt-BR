---
title: Expansor de Configurações Gerais de Servidor de Mediação
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 4/14/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.MediationServerGeneralSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 0e0ad9f0-27d5-4975-ae88-0b8ff8a4c514
ms.openlocfilehash: a149d1a53c79a94572208c405ded3fb54d440fe3
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62384359"
---
# <a name="mediation-server-general-settings-expander"></a>Expansor de Configurações Gerais de Servidor de Mediação
 


## <a name="general-settings"></a>Configurações gerais

FQDN (nome de domínio totalmente qualificado) do Servidor de Mediação ou pool de Servidor de Mediação. Edite o FQDN do servidor para alterar o valor. Você deve ter um registro de hospedeiro (A) DNS (Domain Name System) coincidente com o novo valor.
  
Na seção **Associações** , você seleciona um pool de Servidor de Borda ou Servidor de Borda para associar ao pool de Servidor de Mediação ou Servidor de Mediação. Selecione a Borda que os componentes de mídia do Servidor de Mediação usarão para usuários externos Enterprise Voice.
  
Caso você não possua um Servidor de Borda atualmente definido e precise associar o Servidor de Mediação com um Servidor de Borda, clique em **Novo** e defina o novo pool de Servidor de Borda ou Servidor de Borda no assistente Definir Novo pool de Borda.
  
## <a name="next-hop-settings"></a>Configurações de próximo salto

Você especifica o próximo salto do pool de Servidor de Mediação ou Servidor de Mediação selecionando o pool de Front-Ends Enterprise Edition, ou Servidor Front-Ends Standard Edition, definido a partir da lista suspensa. Um Diretor ou pool de Diretores não é uma seleção válida para um próximo salto de pool de Servidores de Mediação ou de Servidor de Mediação e não aparecerá na lista. Clique **em OK** para aceitar e salvar suas alterações. Clique em **Cancelar** para descartar suas alterações e sair da página de propriedades.
  
## <a name="pstn-gateway-settings"></a>Configurações de gateway PSTN

1. Defina os gateways PSTN associados ao pool de Servidores de Mediação ou ao Servidor de Mediação. Se você já tiver definido gateways, eles estarão disponíveis para associação com o Servidor de Mediação. Se você habilitar a colocação do Servidor de Mediação, defina o intervalo de porta de escuta nos servidores do pool para Transport Layer Security (TLS). Por padrão, essa porta é 5067. Se você selecionar **Habilitar porta TCP**, será necessário definir uma porta TCP (Transmission Control Protocol) para o Servidor de Mediação colocado. Essa é uma configuração opcional, e você deve consultar os requisitos de seu gateway ou requisitos PSTN a fim de determinar se precisa disso. Por padrão, o valor de porta TCP é 5068.
    
2. Troncos associados ao Servidor de Mediação posicionado. Se você já tiver definido os troncos, eles estarão disponíveis para associação com o Servidor de Mediação. 
    
3. Se você tiver mais de um tronco associado a um Servidor de Mediação, poderá especificar um tronco padrão selecionando o tronco e clicando em **Tornar Padrão**. Para desmarcar um gateway como padrão, clique em **Desfazer Padrão**. 
    


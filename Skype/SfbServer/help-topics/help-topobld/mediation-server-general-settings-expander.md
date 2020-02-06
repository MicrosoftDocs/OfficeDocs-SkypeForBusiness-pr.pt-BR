---
title: Expansor de Configurações Gerais de Servidor de Mediação
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/14/2015
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.MediationServerGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0e0ad9f0-27d5-4975-ae88-0b8ff8a4c514
ms.openlocfilehash: 1936034831ca3d66007e7f2186ce3772fbaaa06b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819603"
---
# <a name="mediation-server-general-settings-expander"></a>Expansor de Configurações Gerais de Servidor de Mediação
 


## <a name="general-settings"></a>Configurações gerais

Nome de domínio totalmente qualificado (FQDN) do pool do servidor de mediação ou do servidor de mediação. Edite o FQDN do servidor para alterar o valor. É necessário ter um registro (A) de host de Sistema de Nomes de Domínio (DNS) que coincida com o novo valor.
  
Na seção **associações** , selecione um servidor de borda ou um pool de servidores de borda para associar ao pool do servidor de mediação ou ao servidor de mediação. Você seleciona a borda que os componentes de mídia do servidor de mediação usarão para o usuário externo de voz empresarial.
  
Se você não tiver um servidor de borda atualmente definido e precisar associar o servidor de mediação a um servidor de borda, clique em **novo** e defina o novo servidor de borda ou o pool de servidor de borda no assistente definir o novo pool de borda.
  
## <a name="next-hop-settings"></a>Configurações de próximo salto

Você especifica o pool do servidor de mediação ou o servidor de mediação próximo nó, selecionando o pool de front-end Enterprise Edition definido ou o servidor front-end Standard Edition na lista suspensa. Um diretor ou um pool de diretor não é uma seleção válida para um pool do servidor de mediação ou servidor de mediação próximo salto e não aparecerá na lista. Clique em **OK** para aceitar e salvar as alterações. Clique em **Cancelar** para descartar suas alterações e sair da página de propriedades.
  
## <a name="pstn-gateway-settings"></a>Configurações de gateway PSTN

1. Você define os gateways PSTN associados ao pool do servidor de mediação ou ao servidor de mediação. Se você já definiu gateways, eles estarão disponíveis para serem associados ao servidor de mediação. Se você habilitar a colocação do Servidor de Mediação, defina o intervalo de porta de escuta nos servidores do pool para TLS. Por padrão, essa porta é a 5067. Se você selecionar **Habilitar porta TCP**, será necessário definir uma porta TCP para o Servidor de Mediação colocado. Essa é uma configuração opcional, e você deverá verificar seus requisitos de gateway ou PSTN a fim de determinar se isso é necessário. Por padrão, o valor da porta TCP é 5068.
    
2. Troncos associados ao Servidor de Mediação colocado. Se você já tiver definido os troncos, eles estarão disponíveis para associação com o Servidor de Mediação. 
    
3. Se você tiver mais de um tronco associado a um servidor de mediação, poderá especificar um tronco padrão selecionando o tronco e, em seguida, clicando em **tornar padrão**. Para desmarcar um gateway como padrão, clique em **Desfazer Padrão**. 
    


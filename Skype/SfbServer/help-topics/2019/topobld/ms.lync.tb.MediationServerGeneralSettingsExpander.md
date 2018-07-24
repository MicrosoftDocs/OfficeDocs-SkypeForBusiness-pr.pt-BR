---
title: Expansor de Configurações Gerais de Servidor de Mediação
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MediationServerGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0e0ad9f0-27d5-4975-ae88-0b8ff8a4c514
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 9218b8881bb53e927c6df3635986acb093da8c83
ms.sourcegitcommit: 1f7299f535ec6b34f92301b4abc14d8922492eeb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21059032"
---
# <a name="mediation-server-general-settings-expander"></a>Expansor de Configurações Gerais de Servidor de Mediação
 


## <a name="general-settings"></a>Configurações gerais

Nome de domínio totalmente qualificado (FQDN) do pool do servidor de mediação ou servidor de mediação. Edite o FQDN do servidor para alterar o valor. É necessário ter um registro (A) de host DNS (Sistema de Nome de Domínio) que coincida com o novo valor.
  
Na seção **associações** , você pode selecionar um servidor de borda ou pool de servidores de borda para associar o pool do servidor de mediação ou servidor de mediação. Você seleciona a borda que os componentes de mídia do servidor de mediação usará para o Enterprise Voice de usuário externo.
  
Se você não tiver um servidor de borda definidos atualmente e precisa associar o servidor de mediação um servidor de borda, clique em **novo** e definir o novo servidor de borda ou o pool do servidor de borda em definir o Assistente de pool de borda novo.
  
## <a name="next-hop-settings"></a>Configurações de próximo salto

Especifique o pool do servidor de mediação ou próximo salto do servidor de mediação selecionando o pool definido de Front End do Enterprise Edition ou Standard Edition servidor Front-End da lista suspensa. Um diretor ou diretor pool não é uma seleção válida de um pool do servidor de mediação ou o próximo salto do servidor de mediação e não aparecerão na lista. Clique em **Okey** para aceitar e salvar suas alterações. Clique em **Cancelar** para descartar suas alterações e sair da página de propriedades.
  
## <a name="pstn-gateway-settings"></a>Configurações de gateway PSTN

1. Você define os gateways PSTN associados com o pool do servidor de mediação ou servidor de mediação. Se você já tenha definido gateways, eles estarão disponíveis para associar o servidor de mediação. Se você habilitar a colocação do Servidor de Mediação, defina o intervalo de porta de escuta nos servidores do pool para TLS. Por padrão, essa porta é a 5067. Se você selecionar **Habilitar porta TCP**, será necessário definir uma porta TCP para o Servidor de Mediação colocado. Essa é uma configuração opcional, e você deverá verificar seus requisitos de gateway ou PSTN a fim de determinar se isso é necessário. Por padrão, o valor da porta TCP é 5068.
    
2. Troncos associados ao Servidor de Mediação colocado. Se você já tiver definido os troncos, eles estarão disponíveis para associação com o Servidor de Mediação. 
    
3. Se você tiver mais de um tronco associado a um servidor de mediação, você pode especificar um tronco padrão selecionando o tronco e, em seguida, clicando em **Tornar padrão**. Para desmarcar um gateway como padrão, clique em **Desfazer Padrão**. 
    


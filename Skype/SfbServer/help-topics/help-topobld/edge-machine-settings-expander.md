---
title: Expansor de Configurações de Máquina de Borda
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.EdgeMachineSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 747456dd-d237-44e6-9e64-63b0e7212a08
description: 'Para editar as propriedades de um servidor em um pool de servidores de borda, faça o seguinte:'
ms.openlocfilehash: 93d8169eaaa6c0ca69b9210addea37ac21a8c5b7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820083"
---
# <a name="edge-machine-settings-expander"></a>Expansor de Configurações de Máquina de Borda
 
Para editar as propriedades de um servidor em um pool de servidores de borda, faça o seguinte:
  
O **nome interno ou FQDN** pode ser alterado editando o nome de domínio totalmente qualificado (FQDN). O FQDN deve coincidir com o registro do host (A) do sistema de nomes de domínio (DNS) e o nome do requerente atribuído ao servidor para a interface de rede interna de borda. O valor do **endereço IP interno** define o endereço IP que é atribuído à interface de rede que é definida como uma rede interna, em relação ao design da rede do perímetro.
  
As próximas três seções da caixa de diálogo definem os endereços IP para a configuração externa deste servidor de borda. A capacidade de alterar os endereços IP é afetada pela configuração **habilitar FQDN e endereço IP separados para Webconferência e a/V** nas configurações de propriedades no nível do pool do servidor de borda.
  
## <a name="sip-access"></a>Acesso SIP

Edite o endereço IP externo atribuído à interface de rede para acesso a SIP (protocolo de inicialização de sessão). Esse endereço IP pode ser um endereço IP público ou um endereço no intervalo de endereços IP privados.
  
> [!NOTE]
> Se a configuração **habilitar FQDN e endereço IP separados para Webconferência e a/V** na página de configurações do pool estiver habilitada, somente o endereço IP do acesso SIP estará disponível para edição.
  
## <a name="web-conferencing"></a>Webconferência

Edite o endereço IP externo atribuído à interface de rede para conferência via Web. Esse endereço IP pode ser um endereço IP público ou um endereço no intervalo de endereços IP privados.
  
## <a name="audiovideo"></a>Áudio/vídeo

Edite o endereço IP externo atribuído à interface de rede para áudio/vídeo (A/V). Esse endereço IP pode ser um endereço IP público ou um endereço no intervalo de endereços IP privados.
  
A configuração para o **endereço IP público habilitado para NAT usado** é o endereço público usado pela interface externa para a interface de rede a/V ou o servidor de borda em geral. Se a configuração **habilitar FQDN e o endereço IP separados para Webconferência e A/V** estiver habilitado, o endereço IP público será usado para todas as três interfaces externas.
  


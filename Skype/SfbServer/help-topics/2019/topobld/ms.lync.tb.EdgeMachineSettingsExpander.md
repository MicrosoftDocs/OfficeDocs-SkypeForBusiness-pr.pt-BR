---
title: Expansor de Configurações de Máquina de Borda
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeMachineSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 747456dd-d237-44e6-9e64-63b0e7212a08
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para editar as propriedades de um servidor em um pool de servidores de borda, faça o seguinte:'
ms.openlocfilehash: 1b2fce33b65e744c8ba2f18107d4f6bc5369b8de
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41793799"
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
  


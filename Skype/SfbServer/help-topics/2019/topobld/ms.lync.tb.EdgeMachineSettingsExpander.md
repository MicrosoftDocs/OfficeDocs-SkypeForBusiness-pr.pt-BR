---
title: Expansor de configurações de máquina de borda
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeMachineSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 747456dd-d237-44e6-9e64-63b0e7212a08
description: 'Para editar as propriedades de um servidor em um pool de servidores de borda, faça o seguinte:'
ms.openlocfilehash: 04b8d8efc455203e49aeb81e533604a405e37cc5
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2018
---
# <a name="edge-machine-settings-expander"></a>Expansor de configurações de máquina de borda
 
Para editar as propriedades de um servidor em um pool de servidores de borda, faça o seguinte:
  
O **nome interno ou FQDN** pode ser alterada editando o nome de domínio totalmente qualificado (FQDN). O FQDN deve coincidir com o host (A) registro do sistema de nome de domínio (DNS) e o nome da entidade do certificado atribuído ao servidor da interface de rede de borda interna. O valor de **endereço IP interno** define o endereço IP atribuído a interface de rede que é definida como uma rede interna, em relação ao design da rede de perímetro.
  
As próximas três seções da caixa de diálogo definem os endereços IP para a configuração externa do servidor de borda. A capacidade de alterar os endereços IP é afetada pela definição **FQDN de habilitar separado e endereço IP para Webconferência e A / V** nas configurações de propriedades no servidor de Borda nível do pool.
  
## <a name="sip-access"></a>Acesso SIP

Edite o endereço IP externo que é atribuído à interface de rede para acesso de protocolo de iniciação de sessão (SIP). Esse endereço IP pode ser um endereço IP público ou um endereço no intervalo de endereços IP privado.
  
> [!NOTE]
> Se a configuração **FQDN de habilitar separado e endereço IP para Webconferência e A / V** no pool páginaconfigurações estiver habilitada, somente o endereço IP para acesso do SIP estará disponível para edição.
  
## <a name="web-conferencing"></a>Webconferência

Edite o endereço IP externo que é atribuído à interface de rede para webconferências. Esse endereço IP pode ser um endereço IP público ou um endereço no intervalo de endereços IP privado.
  
## <a name="audiovideo"></a>Áudio/vídeo

Editar o endereço IP externo que é atribuído à interface de rede para áudio/vídeo (A / V). Esse endereço IP pode ser um endereço IP público ou um endereço no intervalo de endereços IP privado.
  
A configuração **endereço IP público do usado habilitado para NAT** é o endereço público usado pela interface externa para ambos os A / V rede interface ou o servidor de borda em geral. Se a configuração **FQDN de habilitar separado e endereço IP para Webconferência e A / V** é habilitada, esse endereço IP público é usado para todas as interfaces externas três.
  


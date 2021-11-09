---
title: Expansor de Configurações de Máquina de Borda
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeMachineSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 747456dd-d237-44e6-9e64-63b0e7212a08
description: 'Para editar propriedades para um servidor em um pool de Servidores de Borda, faça o seguinte:'
ms.openlocfilehash: b04c269102bc11f15e336310323de756d9daa917
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60829005"
---
# <a name="edge-machine-settings-expander"></a>Expansor de Configurações de Máquina de Borda
 
Para editar propriedades para um servidor em um pool de Servidores de Borda, faça o seguinte:
  
O  **Nome interno ou FQDN** pode ser alterado editando o FQDN (nome de domínio totalmente qualificado). O FQDN deve ser correspondente ao registro de hospedeiro (A) DNS (Domain Name System) e o nome de entidade do certificado atribuído ao servidor para a interface de rede de Borda interna. O valor do  **Endereço IP interno** define o endereço IP que está atribuído à interface de rede que está definida como rede interna, relativa ao projeto de rede de perímetro.
  
As três próximas seções do diálogo definem os endereços IP para as configurações externas deste Servidor de Borda. A capacidade de alterar os endereços IP é afetada pela definição  **Habilitar FQDN e endereço IP separados para webconferência e A/V** nas configurações de Propriedades no nível de pool de Servidor de Borda.
  
## <a name="sip-access"></a>Acesso SIP

Edite o endereço IP externo que foi atribuído à interface de rede para o acesso SIP (Session Initiation Protocol). Este endereço IP pode ser um endereço IP público ou um endereço em intervalo de endereço IP privado.
  
> [!NOTE]
> Caso a definição **Habilitar FQDN e endereço IP separados para webconferência e A/V** na página de definições do pool esteja ativa, apenas o endereço IP para o acesso SIP estará disponível para edição.
  
## <a name="web-conferencing"></a>Webconferência

Edite o endereço IP externo que está atribuído à interface de rede para webconferência. Este endereço IP pode ser um endereço IP público ou um endereço em intervalo de endereço IP privado.
  
## <a name="audiovideo"></a>Áudio/vídeo

Edite o endereço IP externo que está atribuído à interface de rede para A/V (áudio/vídeo). Este endereço IP pode ser um endereço IP público ou um endereço em intervalo de endereço IP privado.
  
A definição para  **Endereço IP público habilitado para NAT usado** é o endereço público usado pela interface externa para a interface de rede A/V ou o Servidor de Borda em geral. Caso a definição  **Habilitar FQDN e endereço IP separados para webconferência e A/V** esteja ativada, este endereço IP público é usado para todas as três interfaces externas.
  


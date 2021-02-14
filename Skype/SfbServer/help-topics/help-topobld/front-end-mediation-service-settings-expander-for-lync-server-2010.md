---
title: Expansor de Configurações do Serviço de Mediação de Front End para Lync Server 2010
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FeMediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 37166b87-8a43-42a6-a2aa-5a45bed8a6f3
description: 'Edite as propriedades das configurações do Gateway PSTN do Servidor de Mediação nesta caixa de diálogo. Defina as seguintes configurações:'
ms.openlocfilehash: ad6aab0ce528db01621b1d43a62624d96649e66a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807051"
---
# <a name="front-end-mediation-service-settings-expander-for-lync-server-2010"></a>Expansor de Configurações do Serviço de Mediação de Front-end para Lync Server 2010
 
Edite as propriedades das configurações do **Gateway PSTN do Servidor de Mediação** nesta caixa de diálogo. Defina as seguintes configurações:
  
- Selecione o **Servidor de Mediação** Alocado habilitado se você deseja alocar o Servidor de Mediação com este Servidor De Front End ou pools de Front-End.
    
- **Portas de** escuta: defina as portas nas quais o Servidor de Mediação escutará. É possível definir uma porta para **TLS**, ou transport layer security, ou para **TCP**, ou transport control protocol. Para a entrada da porta TCP ficar disponível, é necessário marcar a caixa de seleção **Habilitar porta TCP**. 
    
    > [!IMPORTANT]
    > Consulte a documentação e as configurações de seu gateway PSTN (rede telefônica pública comutada) para determinar se precisa habilitar e definir os valores de porta TLS, TCP ou ambos. O TLS é um protocolo mais seguro, usando certificados para criptografar o tráfego entre o Servidor de Mediação e o gateway PSTN. Nem todos os gateways PSTN suportam TLS. 
  
- Uma listagem do **Tronco** associado atualmente e existente (ou seja, Troncos SIP [Session Initiation Protocol]), **Gateway** (Gateway PSTN ou IP-PBX) e **Site** (site configurado para o tronco e gateway).
    
- Selecione um Tronco, Gateway e Site e clique em **Tornar Padrão** para definir a seleção como padrão para esse serviço de Mediação. Selecione o padrão atual e clique em **Desfazer Padrão** para remover a seleção como o padrão atual. Em seguida, você seleciona um novo o padrão e clica em **Tornar Padrão**.
    
  **OK** aceita e confirma as alterações na caixa de diálogo.
  
  **Cancelar** descarta as alterações e fecha a caixa de diálogo.
  
  **Ajuda** exibe essa tela de ajuda.
  


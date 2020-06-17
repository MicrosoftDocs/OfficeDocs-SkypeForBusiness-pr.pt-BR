---
title: Atualizar registros de DNS SRV
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Para concluir com êxito este procedimento, você deverá estar conectado no servidor ou domínio como um membro do grupo de Administradores de Domínio ou membro do grupo DnsAdmins.
ms.openlocfilehash: 26bb80618868a2bec03d1de32f6c010869b8cf8c
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753263"
---
# <a name="update-dns-srv-records"></a>Atualizar registros de DNS SRV

Para concluir com êxito este procedimento, você deverá estar conectado no servidor ou domínio como um membro do grupo de Administradores de Domínio ou membro do grupo DnsAdmins.
  
Este tópico descreve como atualizar os registros DNS (sistema de nomes de domínio) após a migração para o Skype for Business Server 2019. Após todos os usuários terem sido movidos para o Skype for Business Server 2019, mas antes de o pool ou diretor herdado ser encerrado, você deve atualizar os registros SRV DNS no seu DNS interno para cada domínio SIP. Este procedimento supõe que o DNS interno tem zonas para os domínios de usuário do SIP.
  
## <a name="to-configure-a-dns-srv-record"></a>Para configurar um registro SRV de DNS

1. No servidor DNS, clique em **Iniciar**, clique em **Ferramentas Administrativas** e em **DNS**.
    
2. Na árvore de console para seu domínio SIP, expanda **zonas de pesquisa direta**, expanda o domínio SIP no qual o Skype for Business Server 2019 está instalado e navegue até a configuração de **_tcp** . 
    
3. No painel direito, clique com o botão direito do mouse em **_sipinternaltls** e selecione **Propriedades**.
    
4. Em **host que oferece esse serviço**, atualize o FQDN do host para apontar para o pool do Skype for Business Server 2019.
    
5. Clique em**OK**.
    
## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a>Para verificar se o FQDN do servidor Standard Edition ou pool de Front-Ends pode ser resolvido

1. Faça logon em um computador cliente no domínio.
    
2. Clique em **Iniciar** e em **Executar**.
    
3. Na caixa **abrir** , digite cmd e clique em **OK**.
    
4. No prompt de comando, digite nslookup _\<FQDN of the Front End pool\>_ ou _\<FQDN of the Standard Edition server\>_ e pressione Enter.
    
5. Verifique se recebeu uma resposta que resolve para o endereço IP apropriado para o FQDN.
    


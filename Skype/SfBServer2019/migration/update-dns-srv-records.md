---
title: Atualizar registros de DNS SRV
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Para concluir este procedimento, você deve estar conectado ao servidor ou domínio como membro do grupo Administradores de domínio ou membro do grupo DnsAdmins.
ms.openlocfilehash: 5cdf98d065abbb57b3cb654c8b770f8f1f87500c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231379"
---
# <a name="update-dns-srv-records"></a>Atualizar registros de DNS SRV

Para concluir este procedimento, você deve estar conectado ao servidor ou domínio como membro do grupo Administradores de domínio ou membro do grupo DnsAdmins.
  
Este tópico descreve como atualizar os registros de sistema de nome de domínio (DNS) após a migração para Skype para Business Server 2019. Depois que todos os usuários foram movidos para Skype para Business Server 2019, mas antes que o pool herdado ou diretor é desativado, você deve atualizar os registros DNS SRV no DNS interno para cada domínio SIP. Este procedimento pressupõe que o DNS interno possui zonas para os domínios de usuário do SIP.
  
## <a name="to-configure-a-dns-srv-record"></a>Para configurar um registro SRV de DNS

1. No servidor DNS, clique em **Iniciar**, clique em **Ferramentas administrativas**e clique em **DNS**.
    
2. Na árvore de console do domínio SIP, expanda **Zonas de pesquisa direta**, expanda o domínio SIP no qual Skype para Business Server 2019 está instalado e navegue até a configuração **TCP** . 
    
3. No painel direito, clique com o botão **sipinternaltls** e selecione **Propriedades**.
    
4. Em **Host que oferece este serviço**, atualize o host FQDN para apontar para o Skype para Business Server 2019 pool.
    
5. Clique em **OK**.
    
## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a>Para verificar se o FQDN do pool de Front-End ou servidor Standard Edition pode ser resolvido

1. Faça logon em um computador cliente no domínio.
    
2. Clique em  **Iniciar ** e em  **Executar **.
    
3. Na caixa **Abrir** , digite cmd e clique em **Okey**.
    
4. No prompt de comando, digite nslookup _ \<FQDN do pool de Front-End\> _ ou _ \<FQDN do servidor Standard Edition\>_, e pressione ENTER.
    
5. Verifique se você recebe uma resposta que resolve o endereço IP apropriado para o FQDN.
    


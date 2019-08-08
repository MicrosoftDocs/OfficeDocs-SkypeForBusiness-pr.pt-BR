---
title: Atualizar registros de DNS SRV
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Para concluir esse procedimento com êxito, você deve estar conectado ao servidor ou ao domínio como membro do grupo Domain admins ou de um membro do grupo DnsAdmins.
ms.openlocfilehash: 5d506c3b2ff70ae776396e8d3a51e71360cdcc83
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36241155"
---
# <a name="update-dns-srv-records"></a>Atualizar registros de DNS SRV

Para concluir esse procedimento com êxito, você deve estar conectado ao servidor ou ao domínio como membro do grupo Domain admins ou de um membro do grupo DnsAdmins.
  
Este tópico descreve como atualizar os registros DNS (sistema de nomes de domínio) após a migração para o Skype for Business Server 2019. Depois que todos os usuários tiverem sido movidos para o Skype for Business Server 2019, mas antes que o pool ou o diretor herdado seja encerrado, você deve atualizar os registros SRV DNS no seu DNS interno para cada domínio SIP. Este procedimento pressupõe que o seu DNS interno tem zonas para seus domínios de usuário SIP.
  
## <a name="to-configure-a-dns-srv-record"></a>Para configurar um registro SRV DNS

1. No servidor DNS, clique em **Iniciar**, clique em **Ferramentas administrativas**e, em seguida, clique em **DNS**.
    
2. Na árvore de console do seu domínio SIP, expanda **zonas de pesquisa direta**, expanda o domínio SIP no qual o Skype for Business Server 2019 está instalado e navegue até a configuração **_ TCP** . 
    
3. No painel direito, clique com o botão direito do mouse em **_sipinternaltls** e selecione **Propriedades**.
    
4. Em **host oferecendo esse serviço**, atualize o FQDN do host para apontar para o pool do Skype for Business Server 2019.
    
5. Clique em **OK**.
    
## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a>Para verificar se o FQDN do servidor de front-end ou do servidor Standard Edition pode ser resolvido

1. Faça logon em um computador cliente no domínio.
    
2. Clique em  **Iniciar ** e em  **Executar **.
    
3. Na caixa **abrir** , digite cmd e clique em **OK**.
    
4. No prompt de comando, digite _ \<FQDN do nslookup do pool\> de front-end_ ou _ \<FQDN do servidor\>Standard Edition_e, em seguida, pressione Enter.
    
5. Verifique se você recebe uma resposta que é resolvida para o endereço IP apropriado para o FQDN.
    


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
ms.localizationpriority: medium
description: Para concluir com êxito este procedimento, você deverá estar conectado no servidor ou domínio como um membro do grupo de Administradores de Domínio ou membro do grupo DnsAdmins.
ms.openlocfilehash: 1b88ada924cbf2cf7f4153acda54584d81946cb0
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58579415"
---
# <a name="update-dns-srv-records"></a>Atualizar registros de DNS SRV

Para concluir com êxito este procedimento, você deverá estar conectado no servidor ou domínio como um membro do grupo de Administradores de Domínio ou membro do grupo DnsAdmins.
  
Este tópico descreve como atualizar os registros DNS (Sistema de Nomes de Domínio) após a migração para Skype for Business Server 2019. Depois que todos os usuários tiverem sido movidos para o Skype for Business Server 2019, mas antes que o pool herdado ou o Diretor seja desativado, você deve atualizar os registros SRV DNS em seu DNS interno para cada domínio SIP. Este procedimento supõe que o DNS interno tem zonas para os domínios de usuário do SIP.
  
## <a name="to-configure-a-dns-srv-record"></a>Para configurar um registro SRV de DNS

1. No servidor DNS, clique em **Iniciar**, clique em **Ferramentas Administrativas** e em **DNS**.
    
2. Na árvore de console do seu domínio SIP, expanda **Zonas** de Busca Encaminhar, expanda o domínio SIP no qual o Skype for Business Server 2019 está instalado e navegue até a configuração **_tcp.** 
    
3. No painel direito, clique com o botão direito do **mouse _sipinternaltls** e selecione **Propriedades**.
    
4. No **Host que oferece esse serviço,** atualize o FQDN do host para apontar para o pool Skype for Business Server 2019.
    
5. Clique em **OK**.
    
## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a>Para verificar se o FQDN do servidor Standard Edition ou pool de Front-Ends pode ser resolvido

1. Faça logon em um computador cliente no domínio.
    
2. Clique em **Iniciar** e em **Executar**.
    
3. Na caixa **Abrir,** digite cmd e clique em **OK**.
    
4. No prompt de comando, digite nslookup _\<FQDN of the Front End pool\>_ ou , e pressione  _\<FQDN of the Standard Edition server\>_ ENTER.
    
5. Verifique se recebeu uma resposta que resolve para o endereço IP apropriado para o FQDN.
    


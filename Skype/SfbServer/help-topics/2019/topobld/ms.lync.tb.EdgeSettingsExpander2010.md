---
title: Editar Expansor de configurações de borda do Lync Server 2010
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74a66817-7092-4b2f-a2af-bc1a2c9e5fed
description: 'Você pode editar as configurações para o servidor de borda ou pool de borda, definindo as seguintes propriedades:'
ms.openlocfilehash: 682412e1a486cc7351f081d903d8db1131367623
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2018
---
# <a name="edit-edge-settings-expander-for-lync-server-2010"></a>Editar Expansor de configurações de borda do Lync Server 2010
 
Você pode editar as configurações para o servidor de borda ou pool de borda, definindo as seguintes propriedades: 
  
 **Geral**
  
- **FQDN do pool interno**: O nome de domínio totalmente qualificado do pool interno é a identidade do servidor de borda ou pool de borda conforme definido no registro de host (A ou AAAA para IPv6) domínio nomes DNS (sistema).
    
- Selecione **Habilitar federação para este pool de borda (porta 5061)** se você deseja habilitar o servidor de borda ou pool de borda para federação com outros parceiros de protocolo de iniciação de sessão.
    
    > [!IMPORTANT]
    > Você só pode definir um servidor de borda ou pool de borda ativamente para federação. A configuração mostrada na captura de tela associada indica que outro pool do servidor de borda ou borda já está configurado para federação. O registro SRV de DNS para federação (_sipfederationtls._tcp.\< nome de domínio externo\>) apontará para o servidor de borda ou pool de borda para federação. 
  
- A **Porta de replicação de configuração interna (HTTPS)**, por padrão, a porta TCP 4443, é a porta que o local (ou seja, local para os servidores de borda) cópia do repositório de gerenciamento Central está sendo replicada. A cópia local do repositório de gerenciamento Central está no banco de dados **RTCLOCAL** no SQL Server em cada computador. A replicação é unidirecional, iniciado a partir do servidor de gerenciamento Central (ou o pool de Front-End ou de servidor Front-End que detém a função de servidor de gerenciamento Central) para os servidores de borda e é uma porta da interface interna.
    
 **Seleção do próximo salto**
  
- Selecione na lista de seu **pool de próximo salto**. Você define um diretor, pool de diretor, pool de Front-End ou de servidor Front-End para assumir essa função. O pool de próximo salto é o servidor ou pool de servidores que aceitará mensagens de SIP de entrada do servidor de borda ou interface interna do pool de borda e enviar saída SIP para a interface interna de borda.
    
    > [!NOTE]
    > O diretor é uma função opcional e se você decidir não implantar os diretores, os servidores Front-End (computador único ou pool) assumirá a função Diretor. 
  
 **Configurações externas**
  
Esta seção das propriedades permite editar propriedades para as configurações externas do servidor de borda ou pool de borda. Estas propriedades estão disponíveis para edição:
  
- Selecione o **FQDN de habilitar separado e endereço IP para Webconferência e A / V** nomes de caixa de seleção se você desejar atribuir diferentes endereços IP e domínio totalmente qualificado para cada serviço de servidor de borda.
    
    > [!NOTE]
    > Se você optar por não marque a caixa de seleção, você deve usar portas separadas para cada serviço de borda. Cada serviço de borda compartilharão o FQDN definido para o serviço de borda de acesso e, portanto, usará o mesmo endereço IP. Cada serviço de borda deve ser identificado exclusivamente um endereço IP distinto e mesma porta, ou o mesmo endereço IP e os valores de porta exclusivo. 
  
- Selecione **uma / serviço de borda V é habilitado para NAT** se você deseja configurar A usar um endereço privado ou outro endereço que ficará oculta atrás de um dispositivo NAT (conversão) de endereço de rede do serviço de borda V /.
    
- Para editar o **serviço de borda de acesso**, definir o **FQDN do Pool** para o serviço de borda de acesso conforme definido no DNS pelo host (A e AAAA se IPv6 for usado) um valor de porta e de registros
    
- Para editar o **serviço de borda de webconferência**, definir um **FQDN do Pool** para o serviço de borda de webconferência conforme definido no DNS pelo host (A e AAAA se IPv6 for usado) um valor de porta e de registros
    
- Para editar o **uma / serviço de borda V**, você define um **FQDN do Pool** para A serviço de borda V conforme definido no DNS pelo host (A e AAAA se IPv6 for usado) / registros e um valor de porta
    
    > [!IMPORTANT]
    > Se você tiver selecionado o **FQDN de habilitar separado e endereço IP para Webconferência e A / V** caixa de seleção, apenas o serviço de borda de acesso FQDN do Pool estarão disponível para edição. Atribua portas distintas para cada um dos três serviços de borda.
  
 **OK** Aceita e confirma as alterações na caixa de diálogo.
  
 **Cancelar** Descarta as alterações e fecha a caixa de diálogo.
  
 **Ajuda** Exibe essa tela de ajuda.
  


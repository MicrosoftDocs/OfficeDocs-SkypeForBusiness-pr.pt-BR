---
title: Editar Expansor de Configurações de Borda para Lync Server 2010
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
- ms.lync.tb.EdgeSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74a66817-7092-4b2f-a2af-bc1a2c9e5fed
description: 'Edite as configurações do servidor de borda ou do pool de bordas configurando as seguintes propriedades:'
ms.openlocfilehash: f483f87ad6c7ba6fa8cfc89e0b5d11899a68119a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820003"
---
# <a name="edit-edge-settings-expander-for-lync-server-2010"></a>Editar Expansor de Configurações de Borda para Lync Server 2010
 
Edite as configurações do servidor de borda ou do pool de bordas configurando as seguintes propriedades: 
  
 **Geral**
  
- **FQDN do pool interno**: o nome de domínio totalmente qualificado do pool interno é a identidade do servidor de borda ou o pool de bordas, conforme definido no registro do host de sistema de nomes de domínio (DNS) do host (A ou aaaa para IPv6).
    
- Selecione **habilitar Federação para este pool de bordas (porta 5061)** se você quiser habilitar o servidor de borda ou o pool de bordas para federação com outros parceiros de protocolo de início de sessão.
    
    > [!IMPORTANT]
    > Você só pode definir um servidor de borda ou um pool de bordas ativamente para Federação. A configuração mostrada na captura de tela associada indica que outro servidor de borda ou um pool de bordas já está configurado para Federação. O registro SRV DNS externo para Federação (_sipfederationtls. _tcp.\< nome\>do domínio externo) apontará para o servidor de borda ou o pool de bordas para Federação. 
  
- A **porta de replicação de configuração interna (https)**, por padrão, na porta TCP 4443, é a porta que a cópia local (ou seja, local para os servidores de extremidade) do repositório de gerenciamento central é replicada. A cópia local do repositório de gerenciamento central está no banco de dados do **RTCLOCAL** no SQL Server em cada computador. A replicação é unidirecional, iniciada a partir do servidor de gerenciamento central (ou, o servidor front-end ou o pool de front-ends que mantém a função de servidor central de gerenciamento) para os servidores de borda e é uma porta de interface interna.
    
  **Seleção do próximo salto**
  
- Selecione para a lista do **próximo pool de saltos**. Você define um director, um pool de directors, um servidor front-end ou um pool de front-end para assumir essa função. O próximo pool de saltos é o servidor ou pool de servidores que aceitará mensagens SIP de entrada do servidor de borda ou da interface interna do pool de bordas e enviará o SIP de saída para a interface interna de Edge.
    
    > [!NOTE]
    > O diretor é uma função opcional e, se você decidir não implantar diretores, os servidores front-end (computador ou pool único) assumirão a função de diretor. 
  
  **Configurações externas**
  
Esta seção das propriedades permite que você edite as propriedades das configurações externas do servidor de borda ou do pool de bordas. Estas propriedades estão disponíveis para edição:
  
- Marque a caixa de seleção **habilitar FQDN e endereço IP separados para Webconferência e a/V,** se você quiser atribuir endereços IP distintos e nomes de domínio totalmente qualificados a cada serviço de servidor de borda.
    
    > [!NOTE]
    > Se você optar por não marcar a caixa de seleção, deverá usar portas separadas para cada serviço de borda. Cada serviço de borda compartilhará o FQDN definido para o serviço de borda de acesso e, portanto, usará o mesmo endereço IP. Cada serviço de borda deve ser identificado exclusivamente por um endereço IP distinto e mesma porta, ou pelo mesmo endereço IP e valores de porta exclusivos. 
  
- Selecione o **serviço de borda a/v está habilitado para NAT** se você quiser configurar o serviço de borda a/v para usar um endereço particular ou outro endereço que ficará oculto atrás de um dispositivo NAT (conversão de endereços de rede).
    
- Para editar o **serviço de borda de acesso**, defina o **FQDN do pool** para o serviço de borda de acesso conforme definido no DNS pelos registros host (A e AAAA se IPv6 são usados) e um valor de porta
    
- Para editar o **serviço de borda de Webconferência**, defina um **FQDN de pool** para o serviço de borda de webconferência, conforme definido no DNS, os registros host (a e AAAA se IPv6 são usados) e um valor de porta
    
- Para editar o **serviço de borda a/v**, você define um **FQDN de pool** para o serviço de borda a/v, conforme definido no DNS por registros host (A e AAAA se IPv6 são usados) e um valor de porta
    
    > [!IMPORTANT]
    > Se você tiver marcado a caixa de seleção **habilitar FQDN e endereço IP separados para Webconferência e a/V** , somente o FQDN do pool de serviços de borda de acesso estará disponível para edição. Atribua portas distintas para cada um dos três serviços de borda.
  
  **OK** Aceita e confirma as alterações na caixa de diálogo.
  
  **Cancelar** Descarta as alterações e fecha a caixa de diálogo.
  
  **Ajuda** Exibe essa tela de ajuda.
  


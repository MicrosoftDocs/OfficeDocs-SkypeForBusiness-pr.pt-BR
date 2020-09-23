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
- CSH
ms.custom:
- ms.lync.tb.EdgeSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74a66817-7092-4b2f-a2af-bc1a2c9e5fed
description: 'Edite as configurações do servidor de borda ou do pool de borda configurando as seguintes propriedades:'
ms.openlocfilehash: ab558edd16370d46d452f4e3d146dbf2153f3d9e
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216112"
---
# <a name="edit-edge-settings-expander-for-lync-server-2010"></a>Editar Expansor de Configurações de Borda para Lync Server 2010
 
Edite as configurações do servidor de borda ou do pool de borda configurando as seguintes propriedades: 
  
 **Geral**
  
- **FQDN do pool interno**: o nome de domínio totalmente qualificado do pool interno é a identidade do servidor de borda ou do pool de borda, conforme definido no registro do host DNS (sistema de nomes de domínio) (A ou aaaa para IPv6).
    
- Selecione **habilitar Federação para este pool de borda (porta 5061)** se você deseja habilitar o servidor de borda ou o pool de borda para federação com outros parceiros de protocolo de início de sessão.
    
    > [!IMPORTANT]
    > Você só pode definir um servidor de borda ou um pool de borda ativamente para Federação. A configuração mostrada na captura de tela associada indica que outro servidor de borda ou pool de borda já está configurado para Federação. O registro SRV de DNS externo para Federação (_sipfederationtls. _tcp. \<external domain name\> ) apontará para o servidor de borda ou o pool de borda para Federação. 
  
- A **porta de replicação de configuração interna (https)**, por padrão, na porta TCP 4443, é a porta na qual a cópia local (ou seja, local para os servidores de borda) do repositório de gerenciamento central é replicada. A cópia local do repositório de gerenciamento central está no banco de dados do **RTCLOCAL** no SQL Server em cada computador. A replicação é unidirecional, iniciada a partir do servidor de gerenciamento central (ou o servidor front-end ou o pool de front-ends que mantém a função de servidor de gerenciamento central) para os servidores de borda e é uma porta de interface interna.
    
  **Seleção de próximo salto**
  
- Selecione para lista seu **Pool de próximo salto**. Você define um diretor, um pool de diretores, o servidor front-end ou o pool de front-ends para assumir essa função. O pool de próximo salto é o servidor ou pool de servidores que aceitará mensagens SIP de entrada da interface interna do servidor de borda ou do pool de borda e enviará SIP de saída para a interface interna da borda.
    
    > [!NOTE]
    > O diretor é uma função opcional e, se você decidir não implantar diretores, os servidores front-end (computador único ou pool) assumirão a função diretor. 
  
  **Configurações externas**
  
Esta seção das propriedades permite que você edite as propriedades das configurações externas do servidor de borda ou do pool de borda. As propriedades a seguir estão disponíveis para edição:
  
- Marque a caixa de seleção **habilitar FQDN e endereço IP separados para Webconferência e a/V** se quiser atribuir endereços IP distintos e nomes de domínio totalmente qualificados a cada serviço de servidor de borda.
    
    > [!NOTE]
    > Se você escolher não marcar a caixa de seleção, deverá usar portas separadas para cada serviço de Borda. Cada serviço de borda compartilhará o FQDN definido para o serviço de borda de acesso e, portanto, usará o mesmo endereço IP. Cada serviço de Borda precisa ser identificado exclusivamente por um endereço IP distinto e pela mesma porta, ou o mesmo endereço IP e valores de porta exclusivos. 
  
- Selecione o **serviço de borda a/v é habilitado para NAT** se quiser configurar o serviço de borda a/v para usar um endereço privado ou outro endereço que ficará oculto atrás de um dispositivo NAT (conversão de endereço de rede).
    
- Para editar o **serviço de borda de acesso**, defina o **FQDN do pool** para o serviço de borda de acesso, conforme definido nos registros DNS pelo host (A, e AAAA se IPv6 for usado) e um valor de porta
    
- Para editar o **serviço de borda de Webconferência**, defina um **FQDN de pool** para o serviço de borda de Webconferência conforme definido no DNS pelos registros de host (a e AAAA se IPv6 for usado) e um valor de porta
    
- Para editar o **serviço de borda a/v**, você define um **FQDN de pool** para o serviço de borda a/v, conforme definido no DNS pelos registros de host (A, e AAAA se IPv6 for usado) e um valor de porta
    
    > [!IMPORTANT]
    > Se você tiver marcado a caixa de seleção **habilitar FQDN e endereço IP separados para Webconferência e a/V** , somente o FQDN do pool de serviços de borda de acesso estará disponível para edição. Atribua portas distintas para cada um dos três serviços de Borda.
  
  **OK** aceita e confirma as alterações na caixa de diálogo.
  
  **Cancelar** descarta as alterações e fecha a caixa de diálogo.
  
  **Ajuda** exibe essa tela de ajuda.
  


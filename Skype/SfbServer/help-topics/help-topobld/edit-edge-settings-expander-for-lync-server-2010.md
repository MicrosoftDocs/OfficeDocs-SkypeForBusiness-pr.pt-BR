---
title: Editar Expansor de Configurações de Borda para Lync Server 2010
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeSettingsExpander2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 74a66817-7092-4b2f-a2af-bc1a2c9e5fed
description: 'Edite as configurações do pool de Borda ou Servidor de Borda configurando as seguintes propriedades:'
ms.openlocfilehash: bb94c152fae183af3198f3fae99501ee33759bca
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60765775"
---
# <a name="edit-edge-settings-expander-for-lync-server-2010"></a>Editar Expansor de Configurações de Borda para Lync Server 2010
 
Edite as configurações do pool de Borda ou Servidor de Borda configurando as seguintes propriedades: 
  
 **Geral**
  
- **FQDN do pool** interno : O nome de domínio totalmente qualificado do pool interno é a identidade do Servidor de Borda ou pool de Borda, conforme definido no registro de host do DNS (sistema de nomes de domínio) (A ou AAAA para IPv6).
    
- Selecione Habilitar federação para esse pool de Borda **(porta 5061)** se quiser habilitar o Servidor de Borda ou pool de Borda para federação com outros parceiros de protocolo de iniciação de sessão.
    
    > [!IMPORTANT]
    > Você só pode definir um Servidor de Borda ou pool de Borda ativamente para federação. A configuração mostrada na captura de tela associada indica que outro Servidor de Borda ou pool de Borda já está configurado para federação. O registro SRV DNS externo para federação (_sipfederationtls._tcp. ) apontará para o Servidor de Borda ou \<external domain name\> pool de Borda para federação. 
  
- A Porta de Replicação de Configuração Interna **(HTTPS)**, por padrão, na porta TCP 4443, é a porta que a cópia local (ou seja, local para os Servidores de Borda) do armazenamento de Gerenciamento Central é replicada. A cópia local do armazenamento de Gerenciamento Central está no banco de dados **RTCLOCAL** no SQL Server em cada computador. A replicação é one-way, iniciada do Servidor de Gerenciamento Central (ou, do Servidor de Front-End ou do pool de Front-End que mantém a função servidor de Gerenciamento Central) para os Servidores de Borda e é uma porta de interface interna.
    
  **Seleção de próximo salto**
  
- Selecione para lista seu **Pool de próximo salto**. Você define diretor, pool de diretores, servidor front-end ou pool de front-end para assumir essa função. O pool de próximo salto é o pool de servidor ou servidor que aceitará mensagens SIP de entrada da interface interna do servidor de Borda ou do pool de Borda e enviará SIP de saída para a interface interna de Borda.
    
    > [!NOTE]
    > O Diretor é uma função opcional e, se você decidir não implantar Diretores, os Servidores Front-End (um único computador ou pool) assumirão a função de Diretor. 
  
  **Configurações externas**
  
Esta seção das propriedades permite editar propriedades para as configurações externas do Servidor de Borda ou pool de Borda. As propriedades a seguir estão disponíveis para edição:
  
- Marque a caixa de seleção Habilitar **FQDN** e endereço IP separados para webconferência e A/V se quiser atribuir endereços IP distintos e nomes de domínio totalmente qualificados a cada serviço do Servidor de Borda.
    
    > [!NOTE]
    > Se você escolher não marcar a caixa de seleção, deverá usar portas separadas para cada serviço de Borda. Cada serviço de Borda compartilhará o FQDN definido para o serviço de Borda de Acesso e, portanto, usará o mesmo endereço IP. Cada serviço de Borda precisa ser identificado exclusivamente por um endereço IP distinto e pela mesma porta, ou o mesmo endereço IP e valores de porta exclusivos. 
  
- Selecione O serviço de Borda **A/V** está habilitado para NAT se você quiser configurar o serviço de Borda A/V para usar um endereço privado ou outro endereço que ficará oculto atrás de um dispositivo NAT (conversão de endereço de rede).
    
- Para editar o serviço de Borda de **Acesso,** defina o **FQDN** do Pool para o serviço de Borda de Acesso, conforme definido em DNS por host (A, e AAAA se IPv6 for usado) e um valor de porta
    
- Para editar o serviço de Borda de **WebConferência,** você define um **FQDN** do Pool para o serviço de Borda de WebConferência, conforme definido em DNS por host (A, e AAAA se IPv6 for usado) e um valor de porta
    
- Para editar o serviço de Borda **A/V,** defina um **FQDN** do Pool para o serviço de Borda A/V, conforme definido no DNS por host (A, e AAAA se IPv6 for usado) e um valor de porta
    
    > [!IMPORTANT]
    > Se você tiver selecionado a caixa de seleção Habilitar FQDN e ENDEREÇO IP separados para webconferência e **A/V,** somente o FQDN do Pool de Serviços de Borda de Acesso estará disponível para edição. Atribua portas distintas para cada um dos três serviços de Borda.
  
  **OK** aceita e confirma as alterações na caixa de diálogo.
  
  **Cancelar** descarta as alterações e fecha a caixa de diálogo.
  
  **Ajuda** exibe essa tela de ajuda.
  


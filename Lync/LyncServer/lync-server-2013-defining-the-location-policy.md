---
title: 'Lync Server 2013: definindo a política de local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the location policy
ms:assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398962(v=OCS.15)
ms:contentKeyID: 48185553
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9842b5bec4b635566288998d6e8110fcc51463d7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048194"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-the-location-policy-for-lync-server-2013"></a>Definir a política de local para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-29_

Cada política de local contém as seguintes informações:

  - **Serviços de emergência habilitados**  
    Quando este valor é **Sim**, o cliente é habilitado para E9-1-1. Quando um cliente se registra, ele tenta adquirir um local do serviço de informações de local e incluirá as informações de local como parte de uma chamada de emergência.

<!-- end list -->

  - **Local necessário**  
    Essa configuração é usada somente quando os **serviços de emergência habilitados** estão definidos como **Sim**.
    
    É possível definir a configuração **Local Necessário** para definir o comportamento do cliente. A definição do valor como **Não** significa que o usuário não receberá uma solicitação de local. A definição do valor como **Sim** significa que o usuário receberá uma solicitação por um local, mas poderá ignorar a solicitação. A definição do valor como **Aviso de isenção de responsabilidade** significa que o usuário receberá uma solicitação por um local e mostrará um aviso de isenção de responsabilidade caso ele tente ignorar a solicitação. Em todos os casos, o usuário pode continuar a usar o cliente.
    
    <div>
    

    > [!NOTE]  
    > O texto do aviso de isenção de responsabilidade não aparecerá se um usuário inserir manualmente um local antes de ser habilitado para E9-1-1. As atualizações para o texto do aviso de isenção de responsabilidade não será visualizado pelos usuários que já visualizaram o aviso de isenção de responsabilidade.

    
    </div>

<!-- end list -->

  - **Isenção de Responsabilidade do Serviço de Emergência Avançado**  
    Esta configuração especifica o aviso de isenção que o usuário ver se ignorar o aviso em um local. No Lync Server 2013, você pode usar a política de local para definir avisos de isenção de responsabilidade diferentes para localidades diferentes ou diferentes conjuntos de usuários.
    
    <div>
    

    > [!NOTE]  
    > Essa configuração de política de local difere do Lync Server 2010, onde você usou o cmdlet <STRONG>set-CsEnhancedEmergencyServiceDisclaimer</STRONG> para definir um aviso global para toda a organização. Se um aviso de isenção global já existir, você precisa especificar o aviso de isenção na política de local. Ou seja, o Lync Server 2013 usa apenas avisos de isenção de responsabilidade especificados na política de local.

    
    </div>

<!-- end list -->

  - **Sequência de discagem de emergência**  
    Esta  sequência de discagem (menos o “+” inicial, mas incluindo qualquer normalização realizada pelo Plano de discagem do usuário do Lync) que significa que uma chamada é uma chamada de emergência. A **Sequência de discagem de emergência** faz com que o cliente inclua na chamada informações sobre o local e sobre retorno de chamada.
    
    <div>
    

    > [!NOTE]  
    > Se sua organização não usa um prefixo de acesso de linha externa, não será necessário criar uma regra de normalização do Plano de discagem correspondente que acrescenta um “+” à sequência 911 antes de enviar a chamada ao Roteamento de saída em um servidor de pool do Lync; o “+” será automaticamente pré-demarcado pelo cliente do Lync como resultado da política de local. No entanto, se seu site usar um prefixo de acesso externo, é necessário adicionar uma regra de normalização à política de Plano de discagem aplicável que retira o prefixo de acesso externo e adiciona o “+”. Por exemplo, se seu local usar um prefixo de acesso externo 9 e um usuário discar 9&nbsp;911 para fazer uma chamada de emergência, o cliente usará sua política de plano de discagem para normalizar isso para + 911 antes que o número discado seja avaliado pelas rotas no perfil de local do chamador.

    
    </div>

<!-- end list -->

  - **Máscaras da sequência de discagem de emergência**  
    Uma lista separada por ponto e vírgula de sequências de discagem a serem traduzidas para a **Sequência de discagem de emergência**. Por exemplo, você pode querer adicionar 112, que é o número do serviço de emergência em grande parte da Europa. Talvez um usuário do Lync vindo da Europa não saiba que 911 é o número de emergência nos EUA, mas ele pode discar 112 e obter o mesmo resultado. Assim como ocorre com a Sequência de discagem de emergência, não inclua um “+” antes de cada número e se você usar os códigos de acesso de linha externa, certifique-se de que existam regras de normalização na política de Plano de discagem do usuário para retirar o dígito do código de acesso.

<!-- end list -->

  - **Uso de PSTN**  
    O nome do Uso de PSTN que contém os caminhos de roteamento que determinam para qual tronco SIP, gateway PSTN ou gateway ELIN as chamadas serão encaminhadas.
    
    <div>
    

    > [!NOTE]  
    > É possível atribuir apenas um Uso a uma política de local. Esse Uso de PSTN substitui os Usos de PSTN atribuídos à política de voz do usuário, mas se aplica somente às chamadas feitas para a Sequência de discagem de emergência ou uma das Máscaras de sequência de chamada de emergência.

    
    </div>

<!-- end list -->

  - **URI de notificação**  
    Especifica um ou mais URIs SIP do pessoal de segurança que receberá uma notificação de mensagem instantânea (IM) quando uma chamada de emergência for realizada. Os grupos de distribuição são suportados.

<!-- end list -->

  - **URI de conferência**  
    Especifica um número DID (discagem direta interna) (normalmente um número do suporte de segurança) que deve ser verificado quando uma chamada de emergência é feita.

<!-- end list -->

  - **Modo de conferência**  
    Especifica se o URI de conferência será inserido na chamada de emergência usando comunicação de uma ou duas vias.

<!-- end list -->

  - **Intervalo de atualização de local**  
    Especifica a quantidade de tempo (em horas) entre as solicitações de cliente para uma atualização de local do serviço de informações de local. O valor pode ser definido para qualquer valor entre 1 e 12. O valor padrão é 4.

</div>

<span> </span>

</div>

</div>

</div>


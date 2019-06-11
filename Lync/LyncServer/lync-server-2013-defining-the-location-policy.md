---
title: 'Lync Server 2013: definindo a política de localização'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining the location policy
ms:assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398962(v=OCS.15)
ms:contentKeyID: 48185553
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26b0e9aca4b3e66202d6b3c4a47b90db4f207fda
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829710"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-the-location-policy-for-lync-server-2013"></a>Definindo a política de localização do Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-29_

Cada política de local contém as seguintes informações:

  - **Serviços de emergência habilitados**  
    Quando esse valor é **Sim**, o cliente está habilitado para E9-1-1. Quando um cliente é registrado, ele tenta adquirir um local do serviço de informações de localização e inclui as informações de localização como parte de uma chamada de emergência.

<!-- end list -->

  - **Local obrigatório**  
    Essa configuração é usada somente quando os **serviços de emergência habilitados** são definidos como **Sim**.
    
    Você pode configurar a configuração de **localização necessária** para definir o comportamento do cliente. Definir o valor como **Não** significa que o usuário não receberá uma solicitação de local. Definir o valor como **Sim** significa que o usuário receberá uma solicitação de local, mas poderá ignorá-la. Definir o valor como **Aviso de isenção de responsabilidade** significa que o usuário receberá uma solicitação de local e um aviso de isenção de responsabilidade caso tente ignorar a solicitação. De qualquer forma, o usuário pode continuar utilizando o cliente.
    
    <div>
    

    > [!NOTE]  
    > O texto do aviso de isenção de responsabilidade não aparecerá se um usuário inserir manualmente um local antes de ser habilitado para E9-1-1. As atualizações para o texto do aviso de isenção de responsabilidade não será visualizado pelos usuários que já visualizaram o aviso de isenção de responsabilidade. 

    
    </div>

<!-- end list -->

  - **Aviso de Isenção de Responsabilidade do Serviço de Emergência Avançado**  
    Esta configuração especifica o aviso de isenção de responsabilidade que o usuário verá caso ignore a solicitação de local. No Lync Server 2013, você pode usar a política de localização para definir avisos de isenção de responsabilidade diferentes para locais diferentes ou conjuntos de usuários diferentes.
    
    <div>
    

    > [!NOTE]  
    > Essa configuração de política de localização é diferente do Lync Server 2010, no qual você usou o cmdlet <STRONG>set-CsEnhancedEmergencyServiceDisclaimer</STRONG> para definir um aviso global para a organização inteira. Se já existir uma isenção global, você precisará especificar essa isenção de responsabilidade na política de localização. Ou seja, o Lync Server 2013 usa apenas avisos de isenção especificados na política de localização.

    
    </div>

<!-- end list -->

  - **Cadeia de discagem de emergência**  
    Esta cadeia de caracteres de discagem (menos a "+" à esquerda, mas incluindo qualquer normalização feita pelo plano de discagem do usuário do Lync) significa que uma chamada é uma chamada de emergência. A **Sequência de discagem de emergência** faz com que o cliente inclua na chamada informações sobre o local e sobre retorno de chamada.
    
    <div>
    

    > [!NOTE]  
    > Se a sua organização não usar um prefixo de acesso de linha externa, você não precisará criar uma regra de normalização de plano de discagem correspondente que adiciona "+" à cadeia de caracteres 911 antes de enviar a chamada para o roteamento de saída em um servidor de pool do Lync; o "+" será automaticamente retomado pelo cliente do Lync como resultado da política de localização. No entanto, se seu site usar um prefixo de acesso externo, será necessário adicionar uma regra de normalização à política de Plano de Discagem aplicável que remove o prefixo de acesso externo e adiciona “+”. Por exemplo, se a sua localização usa um prefixo de acesso externo de 9 e um usuário discar 9&nbsp;911 para fazer uma chamada de emergência, o cliente usará sua política de plano de discagem para normalizar isso para + 911 antes que o número discado seja avaliado por rotas na localização do chamador Profile.

    
    </div>

<!-- end list -->

  - **Máscaras de cadeias de discagem de emergência**  
    Uma lista separada por ponto-e-vírgula de cadeias de discagem que é traduzida para a cadeia de discagem de **emergência**especificada Por exemplo, talvez você queira adicionar 112, que é o número do serviço de emergência para a maioria da Europa. Um usuário visitante do Lync da Europa talvez não saiba que 911 é o número de emergência dos EUA, mas pode discar o 112 e obter o mesmo resultado. Assim como na cadeia de caracteres de discagem de emergência, não inclua um "+" antes de cada número e, se você usar códigos de acesso de linha externos, certifique-se de que haja regras de normalização na política de plano de discagem do usuário para retirar o dígito de código de acesso.

<!-- end list -->

  - **Uso de PSTN**  
    O nome do Uso de PSTN que contém os caminhos de roteamento que determinam para qual tronco SIP, gateway PSTN ou gateway ELIN as chamadas serão encaminhadas.
    
    <div>
    

    > [!NOTE]  
    > É possível atribuir apenas um Uso a uma política de local. Esse Uso de PSTN substitui os Usos de PSTN atribuídos à política de voz do usuário, mas se aplica somente às chamadas feitas para a Sequência de discagem de emergência ou uma das Máscaras de sequência de chamada de emergência.

    
    </div>

<!-- end list -->

  - **URI de notificação**  
    Especifica um ou mais URIs SIP do pessoal de segurança que receberá uma notificação de IM (Sistema de Mensagens Instantâneas) quando uma chamada de emergência for realizada. Há suporte para grupos de distribuição.

<!-- end list -->

  - **URI de Conferência**  
    Especifica um número DID (discagem direta interna) (normalmente um número do suporte de segurança) que deve ser verificado quando uma chamada de emergência é feita.  

<!-- end list -->

  - **Modo de Conferência**  
    Especifica se o URI de conferência será inserido na chamada de emergência usando comunicação de uma ou duas vias. 

<!-- end list -->

  - **Intervalo de Atualização de Local**  
    Especifica a quantidade de tempo (em horas) entre as solicitações do cliente para uma atualização de localização do serviço de informações de localização. O valor pode ser definido para qualquer valor entre 1 e 12. O valor padrão é 4.

</div>

<span> </span>

</div>

</div>

</div>


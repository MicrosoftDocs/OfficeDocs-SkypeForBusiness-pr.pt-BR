---
title: 'Lync Server 2013: Validando o roteamento e a normalização do número de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating voice number normalization and routing
ms:assetid: a6a825c7-6928-4e80-b7e9-803b7f7ebd13
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720922(v=OCS.15)
ms:contentKeyID: 63969633
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16739595878b0c67b37f988295a4b02877a3a6fd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757925"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-voice-number-normalization-and-routing-in-lync-server-2013"></a>Validando a normalização de número de voz e encaminhamento no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-05-19_

A normalização e o roteamento do número corretos são muito importantes para o ambiente corporativo de voz funcional. Especialmente durante as migrações do PBX (Private Branch Exchange) para o ambiente autônomo do Lync Server, uma das chaves para a migração bem-sucedida é revelar e documentar todas as regras de discagem existentes e criar regras de normalização adequadas, políticas de voz usos e rotas de telefone.

A validação da normalização do número e do roteamento é importante não apenas durante as migrações, mas também durante a operação normal e estável do sistema.

Recomendamos realizar essa validação diariamente usando o painel de controle do Lync Server, começando com o desenvolvimento de um conjunto robusto de casos de teste em relação ao conjunto atual de regras de normalização que foram publicadas nas configurações globais do Lync Server. Estes casos de teste devem ser executados diariamente para realçar as alterações indesejadas que foram feitas e confirmadas no plano de discagem.

O painel de controle do Lync Server também ajuda você a Visualizar, testar, alterar, arquivar e compartilhar informações de configuração sobre o roteamento de voz e alterar as regras de normalização do número da empresa, planos de discagem, política de voz e rotas. Ele tem recursos adicionais para fazer o seguinte:

  - Exportar e importar ou fazer backup de dados de roteamento de voz entre sistemas.

  - Testar alterações de configuração antes de carregá-las em um sistema dinâmico.

  - Criar e executar casos de teste de configuração para ajudar a garantir a usabilidade de dados de roteamento depois de fazer alterações nele, mas antes de confirmá-los as alterações em um sistema implantado.

  - Criar e alterar regras de normalização de número, perfis de localização, política de voz e dados de roteamento sem escrever as expressões regulares necessárias.

  - Analisando um perfil de local para compatibilidade com o Lync Server Phone Edition.

  - Mais informações sobre testes de roteamento de voz podem ser encontradas em [testar roteamento de voz no Lync Server 2013](lync-server-2013-test-voice-routing.md)

<div>

## <a name="see-also"></a>Confira também


[Testar roteamento de voz no Lync Server 2013](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


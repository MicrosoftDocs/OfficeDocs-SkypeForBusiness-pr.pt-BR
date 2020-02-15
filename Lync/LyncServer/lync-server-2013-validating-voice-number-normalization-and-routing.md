---
title: 'Lync Server 2013: validação de normalização de número de voz e roteamento'
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
ms.openlocfilehash: cbc15dc47a7eeee0b7fb4bd49ba5ea2584e94fe7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007380"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-voice-number-normalization-and-routing-in-lync-server-2013"></a>Validação da normalização de número de voz e roteamento no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-05-19_

A normalização e o roteamento do número corretos são muito importantes para o ambiente corporativo de voz funcional. Especialmente durante as migrações do PBX (Private Branch Exchange) para o ambiente do Lync Server autônomo, uma das chaves para a migração bem-sucedida é revelar e documentar todas as regras de discagem existentes e criar regras de normalização apropriadas, políticas de voz usos e rotas de telefone.

A validação do número normalização e o roteamento é importante não apenas durante as migrações, mas também durante a operação estável normal do sistema.

Recomendamos realizar essa validação diariamente usando o painel de controle do Lync Server, começando com o desenvolvimento de um conjunto robusto de casos de teste em relação ao conjunto atual de regras de normalização publicadas nas configurações globais do Lync Server. Estes casos de teste devem ser executados diariamente para realçar quaisquer alterações indesejadas que foram feitas e confirmadas no plano de discagem.

O painel de controle do Lync Server também ajuda você a Visualizar, testar, alterar, arquivar e compartilhar informações de configuração sobre o roteamento de voz e alterar as regras de normalização do número Enterprise Voice, planos de discagem, política de voz e rotas. Ele tem recursos adicionais para fazer o seguinte:

  - Exportação e importação ou backup de dados de roteamento de voz entre sistemas.

  - Testar as alterações de configuração antes de carregá-las em um sistema ativo.

  - Criar e executar casos de teste de configuração para ajudar a garantir a usabilidade dos dados de roteamento depois que você fizer alterações nele, mas antes de confirmar as alterações em um sistema implantado.

  - Criar e alterar as regras de normalização de número, perfis de local, política de voz e dados de roteamento sem gravar as expressões regulares necessárias.

  - Análise de um perfil de local para compatibilidade com o Lync Server Phone Edition.

  - É possível encontrar mais informações sobre testes de roteamento de voz no [Test Voice Routing in Lync Server 2013](lync-server-2013-test-voice-routing.md)

<div>

## <a name="see-also"></a>Confira também


[Testar roteamento de voz no Lync Server 2013](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


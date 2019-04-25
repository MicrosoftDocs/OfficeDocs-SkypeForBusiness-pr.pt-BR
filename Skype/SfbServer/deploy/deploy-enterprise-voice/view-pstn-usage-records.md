---
title: Exibir registros de uso PSTN em Skype para negócios
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 65025c78-c263-472c-9ff9-e170588f10b5
description: 'Resumo: Saiba como exibir registros de uso PSTN usando-se o Skype para painel de controle do Business Server ou o Skype para Business Server Management Shell.'
ms.openlocfilehash: ee3260c79da4619e6093f5e4eff3f98d697b3c19
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32222545"
---
# <a name="view-pstn-usage-records-in-skype-for-business"></a>Exibir registros de uso PSTN em Skype para negócios

**Resumo:** Saiba como exibir registros de uso do PSTN, usando o Skype para painel de controle do Business Server ou o Skype do Shell de gerenciamento do servidor de negócios.

Um registro de uso de Rede Telefônica Pública Comutada (PSTN) especifica uma classe de chamada (por exemplo, interna, local ou interurbana) que pode ser feita por vários usuários ou grupos de usuários em uma organização. Para obter detalhes, consulte [PSTN Usage Records](https://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx) na documentação de planejamento.

### <a name="to-view-a-pstn-usage-record-by-using-skype-for-business-server-control-panel"></a>Para exibir um registro de uso PSTN usando Skype para o painel de controle do servidor de negócios

1. Abra o Skype para painel de controle do servidor de negócios.

2. Na barra de navegação esquerda, clique em **Roteamento de voz** e em **Uso do PSTN**.

3. Na página **Uso do PSTN**, destaque o registro de uso PSTN que você deseja exibir, clique em **Editar** e em **Mostrar detalhes**.

    > [!NOTE]
    > Uma página somente leitura do registro de uso PSTN selecionado mostra as rotas associadas e as políticas de voz associadas.

### <a name="to-view-pstn-usage-information-by-using-skype-for-business-server-management-shell-cmdlets"></a>Para exibir informações de uso do PSTN, usando Skype para cmdlets do Shell de gerenciamento do servidor de negócios

- Para exibir informações sobre todos os usos de PSTN, digite o seguinte comando no Skype do Shell de gerenciamento do servidor de negócios e pressione ENTER:

  ```
  Get-CsPstnUsage
  ```

    Este comando retorna informações semelhantes para o seguinte:

<pre>
  Identity : Global
  Usage    : {Internal, Local, Long Distance}
</pre>

## <a name="see-also"></a>Confira também

[Criar ou modificar uma política de voz e configurar registros de uso PSTN no Skype para negócios](voice-policy-and-pstn-usage-records.md)


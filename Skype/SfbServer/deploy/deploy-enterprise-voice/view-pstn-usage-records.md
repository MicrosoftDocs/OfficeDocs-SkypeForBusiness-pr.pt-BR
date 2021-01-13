---
title: Exibir registros de uso de PSTN no Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 65025c78-c263-472c-9ff9-e170588f10b5
description: 'Resumo: Saiba como exibir registros de uso de PSTN usando o Painel de Controle do Skype for Business Server ou o Shell de Gerenciamento do Skype for Business Server.'
ms.openlocfilehash: abf9f3ec9ce1e2801de2c6017d12fd64df0c8954
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830531"
---
# <a name="view-pstn-usage-records-in-skype-for-business"></a>Exibir registros de uso de PSTN no Skype for Business

**Resumo:** Saiba como exibir registros de uso de PSTN usando o Painel de Controle do Skype for Business Server ou o Shell de Gerenciamento do Skype for Business Server.

Um registro de uso da Rede Telefônica Pública Comutado (PSTN) especifica uma classe de chamada (como interna, local ou interurbano) que pode ser feita por vários usuários ou grupos de usuários em uma organização. Para obter detalhes, consulte [PSTN Usage Records](https://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx) in the Planning documentation.

### <a name="to-view-a-pstn-usage-record-by-using-skype-for-business-server-control-panel"></a>Para exibir um registro de uso de PSTN usando o Painel de Controle do Skype for Business Server

1. Abra o Painel de Controle do Skype for Business Server.

2. Na barra de navegação esquerda, clique em **Roteamento de** Voz e clique em **Uso de PSTN.**

3. Na página **Uso de PSTN,** realça o registro de uso de PSTN que você deseja exibir, clique em **Editar** e em **Mostrar detalhes.**

    > [!NOTE]
    > Uma página somente leitura do registro de uso PSTN selecionado mostra as rotas associadas e as políticas de voz associadas.

### <a name="to-view-pstn-usage-information-by-using-skype-for-business-server-management-shell-cmdlets"></a>Para exibir informações de uso de PSTN usando cmdlets do Shell de Gerenciamento do Skype for Business Server

- Para exibir informações sobre todos os seus usos de PSTN, digite o seguinte comando no Shell de Gerenciamento do Skype for Business Server e pressione ENTER:

  ```powershell
  Get-CsPstnUsage
  ```

    Esse comando retornará informações parecidas com:

<pre>
  Identity : Global
  Usage    : {Internal, Local, Long Distance}
</pre>

## <a name="see-also"></a>Confira também

[Criar ou modificar uma política de voz e configurar registros de uso de PSTN no Skype for Business](voice-policy-and-pstn-usage-records.md)


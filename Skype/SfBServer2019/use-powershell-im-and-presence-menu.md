---
title: Usar o PowerShell para tarefas no menu IM e Presença
ms.reviewer: ''
ms.author: ankum
author: ankum
manager: ravrao
ms.date: 11/03/2021
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: ''
description: 'Resumo: Skype for Business Server painel de controle para mapeamento de Cmdlet para menu IM e Presença.'
ms.openlocfilehash: 9d57e249fb839894454c05d25e78320153d4a306
ms.sourcegitcommit: 11a803d569a57410e7e648f53b28df80a53337b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2021
ms.locfileid: "60888724"
---
# <a name="im-and-presence"></a>IM e presença

Este artigo descreve como resultados semelhantes aos do item de menu **IM** e Presença no Painel de Controle herdado podem ser obtidos usando cmdlets.

Este artigo descreve os seguintes sub-menus:

- [IM e Presença](#im-and-presence)
  - [Filtro de Arquivo](#file-filter)
  - [Filtro de URL](#url-filter)

## <a name="file-filter"></a>Filtro de Arquivo

**O** sub menu FILTRO DE ARQUIVO permite que os administradores gerenciem configurações de filtro de transferência de arquivos na organização. Essas configurações são usadas para bloquear a capacidade do usuário de transferir determinados tipos de arquivos (por exemplo, arquivos com uma extensão de arquivo .vbs ou .ps1) usando um cliente Skype for Business Server.

Considere as várias tarefas que um usuário pode realizar no **FILE FILTER** e os cmdlets Skype for Business essas tarefas são mapeados.

---

> **Cenário 1**: Listar todos os filtros de arquivo

   ![Filtro de Arquivo de Lista](./media/file-filter-1.png)

***Cmdlet***

[Get-CsFileTransferFilterConfiguration](/powershell/module/skype/get-csfiletransferfilterconfiguration)

***Exemplo***

```powershell
 Get-CsFileTransferFilterConfiguration
```

---

> **Cenário 2**: Criar um novo filtro de arquivo

   ![Criar Filtro de Arquivo](./media/file-filter-2.png)

***Cmdlet***

[New-CsFileTransferFilterConfiguration](/powershell/module/skype/new-csfiletransferfilterconfiguration)  

***Exemplo***

```powershell
 New-CsFileTransferFilterConfiguration -Identity site:Redmond
```

---

> **Cenário 3**: Obter detalhes de um filtro de arquivo escolhido

   ![Obter Filtro de Arquivo](./media/file-filter-3.png)

***Cmdlet***

[Get-CsFileTransferFilterConfiguration](/powershell/module/skype/get-csfiletransferfilterconfiguration)

***Exemplo***

```powershell
 Get-CsFileTransferFilterConfiguration -Identity site:Redmond
```

---

> **Cenário 4**: Excluir filtros de arquivo escolhidos

   ![Excluir Filtro de Arquivo](./media/file-filter-4.png)

***Cmdlet***

[Remove-CsFileTransferFilterConfiguration](/powershell/module/skype/remove-csfiletransferfilterconfiguration)

***Exemplo***

```powershell
 Remove-CsFileTransferFilterConfiguration -Identity site:Redmond
```

---

> **Cenário 5**: Atualizar um filtro de arquivo

   ![Atualizar filtro de arquivo](./media/file-filter-5.png)

***Cmdlet***

[Set-CsFileTransferFilterConfiguration](/powershell/module/skype/set-csfiletransferfilterconfiguration)

***Exemplo***

```powershell
 Set-CsFileTransferFilterConfiguration -Identity site:Redmond -Extensions @{Add=".ps1"}
```

---

## <a name="url-filter"></a>Filtro de URL

O item do sub-menu **FILTRO** DE URL em **IM** e Presença permite que os administradores configurem o filtro de URL para que os hiperlinks com determinados prefixos sejam bloqueados ou não sejam ativos. (Em outras palavras, os participantes não podem simplesmente clicar no link e ir para o site ao que o URI se refere; eles devem copiar e colar o link manualmente em um navegador.)

Considere as várias tarefas que um usuário pode realizar no **URL FILTER** e os cmdlets Skype for Business essas tarefas são mapeados.

---
> **Cenário 1**: Listar todos os filtros de URL da Web

   ![Listar filtro DE URL](./media/url-filter-1.png)

***Cmdlet***

[Get-CsImFilterConfiguration](/powershell/module/skype/get-csimfilterconfiguration)

***Exemplo***

```powershell
 Get-CsImFilterConfiguration
```

---

> **Cenário 2**: Criar um novo filtro de URL

   ![Novo filtro de URL](./media/url-filter-2.png)

***Cmdlet***

[New-CsImFilterConfiguration](/powershell/module/skype/new-csimfilterconfiguration)  

***Exemplo***

```powershell
 New-CsImFilterConfiguration -Identity site:Redmond
```

---

> **Cenário 3**: Obter detalhes de um filtro DE URL escolhido

   ![Obter filtro URL](./media/url-filter-3.png)

***Cmdlet***

[Get-CsImFilterConfiguration](/powershell/module/skype/get-csimfilterconfiguration)

***Exemplo***

```powershell
 Get-CsImFilterConfiguration -Identity site:Redmond
```

---

> **Cenário 4**: Excluir filtros de URL escolhidos

   ![Excluir filtro DE URL](./media/url-filter-4.png)

***Cmdlet***

[Remove-CsImFilterConfiguration](/powershell/module/skype/remove-csimfilterconfiguration)

***Exemplo***

```powershell
 Remove-CsImFilterConfiguration -Identity site:Redmond
```

---

> **Cenário 5**: Atualizar um filtro de URL

   ![Atualizar filtro DE URL](./media/url-filter-5.png)

***Cmdlet***

[Set-CsImFilterConfiguration](/powershell/module/skype/set-csimfilterconfiguration)

***Exemplo***

```powershell
 Set-CsImFilterConfiguration -Identity site:Redmond -Enabled $False
```

---

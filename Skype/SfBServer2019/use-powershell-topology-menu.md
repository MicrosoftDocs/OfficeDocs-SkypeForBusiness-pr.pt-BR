---
title: Usar o PowerShell para tarefas no menu Topologia
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
description: 'Resumo: Skype for Business Server painel de controle para mapeamento de cmdlet para menu Topologia.'
ms.openlocfilehash: da5374863d7b9e7c8217802ce98e10cfdab92e54
ms.sourcegitcommit: 3b5ae6ebf4384166c628f66a4f17e6fe4455b708
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/29/2021
ms.locfileid: "61625972"
---
# <a name="topology"></a>Topologia

Este artigo descreve como resultados semelhantes aos do item de menu **Topologia** no Painel de Controle herdado podem ser obtidos usando cmdlets.

Este artigo descreve os seguintes sub-menus:

- [Topologia](#topology)
  - [Status](#status)
  - [Aplicativo do Servidor](#server-application)
  - [URL simples](#simple-url)
  - [Aplicativo Confiável](#trusted-application)

## <a name="status"></a>Status

**O** sub-menu STATUS permite que os administradores gerenciem os computadores na topologia.

Considere as várias tarefas que um usuário pode realizar no **STATUS** e os cmdlets Skype for Business essas tarefas são mapeados.

---

> **Cenário 1**: listar todos os computadores e seu status

   ![Listar Computador e Status](./media/topology-status-1.png)

   ***Cmdlet***

   [Get-CsPool](/powershell/module/skype/get-cspool)

   ***Exemplo***

   ```powershell
    Get-CsPool
   ```

   ***Cmdlet***

   [Get-CsComputer](/powershell/module/skype/get-cscomputer)

   ***Exemplo***

   ```powershell
    Get-CsComputer
   ```

   ***Cmdlet***

   [Get-CsManagementStoreReplicationStatus](/powershell/module/skype/get-csmanagementstorereplicationstatus)

   ***Exemplo***

   ```powershell
   Get-CsManagementStoreReplicationStatus
   ```

---

## <a name="server-application"></a>Aplicativo do Servidor

Os aplicativos de servidor referem-se aos programas individuais executados em Skype for Business Server. **O** sub menu APLICATIVO DO SERVIDOR fornece uma maneira para os administradores retornarem informações sobre qualquer (ou todos) aplicativos em execução como parte do Skype for Business Server.

Considere as várias tarefas que um usuário pode realizar no **APLICATIVO SERVIDOR** e os cmdlets Skype for Business essas tarefas são mapeados.

---
> **Cenário 1**: Listar todos os aplicativos de servidor

   ![Aplicativo de Servidor de Lista](./media/server-application-1.png)

***Cmdlet***

[Get-CsServerApplication](/powershell/module/skype/get-csserverapplication)

***Exemplo***

```powershell
 Get-CsServerApplication
```

---

> **Cenário 2**: Habilitar/Desabilitar ou selecionar crítico/não selecionado crítico de um aplicativo de servidor

   ![Editar Aplicativo do Servidor](./media/server-application-2.png)

***Cmdlet***

[Set-CsServerApplication](/powershell/module/skype/get-csserverapplication)

***Exemplo***

```powershell
 Set-CsServerApplication -Identity "Registrar:atl-cs-001.litwareinc.com/ExumRouting" -Enabled $True
```

---

## <a name="simple-url"></a>URL simples

As URLs simples facilitam a entrada dos usuários em reuniões e conferências e também facilitam o logon dos administradores no Painel de Controle do Skype for Business Server. O sub menu **URL SIMPLES** ajuda o administrador a exibi-los.

Considere as várias tarefas que um usuário pode realizar em **URL SIMPLES** e os cmdlets Skype for Business essas tarefas são mapeados.

---
> **Cenário 1**: listar todas as configurações de URL simples

   ![Listar URL simples](./media/simple-url-1.png)

***Cmdlet***

[Get-CsSimpleUrlConfiguration](/powershell/module/skype/get-cssimpleurlconfiguration)

***Exemplo***

```powershell
 Get-CsSimpleUrlConfiguration | Select-Object -ExpandProperty SimpleUrl
```

---

## <a name="trusted-application"></a>Aplicativo Confiável

Um aplicativo confiável é um aplicativo desenvolvido por terceiros que recebe status confiável para ser executado como parte do Skype for Business Server, mas que não é uma parte interno do produto. O sub menu **APLICATIVO CONFIÁVEL** ajuda o administrador a exibi-los.

Vamos considerar as várias tarefas que um usuário pode realizar no **APLICATIVO CONFIÁVEL** e os cmdlets Skype for Business essas tarefas são mapeados.

---
> **Cenário 1**: listar todos os aplicativos confiáveis

   ![Listar aplicativo confiável](./media/trusted-application-1.png)

***Cmdlet***

[Get-CsTrustedApplication](/powershell/module/skype/get-cstrustedapplication)

***Exemplo***

```powershell
 Get-CsTrustedApplication
```

---

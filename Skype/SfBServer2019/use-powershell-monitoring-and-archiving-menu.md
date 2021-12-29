---
title: Usar o PowerShell para tarefas no menu Monitoramento e Arquivamento
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
description: 'Resumo: Skype for Business Server painel de controle para mapeamento de Cmdlet para o menu Monitoramento e Arquivamento.'
ms.openlocfilehash: b286cf1ad1f52e67c4e4171402927c24908aa4ac
ms.sourcegitcommit: 3b5ae6ebf4384166c628f66a4f17e6fe4455b708
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/29/2021
ms.locfileid: "61625973"
---
# <a name="monitoring-and-archiving"></a>Monitoramento e arquivamento

Este artigo descreve como resultados semelhantes aos do **item** de menu Monitoramento e Arquivamento no Painel de Controle herdado podem ser obtidos usando cmdlets.

Este artigo descreve os seguintes sub-menus:

- [Monitoramento e Arquivamento](#monitoring-and-archiving)
  - [Registro de Detalhes de Chamada](#call-detail-recording)
  - [Qualidade dos dados da experiência](#quality-of-experience-data)
  - [Política de arquivamento](#archiving-policy)
  - [Configuração de Arquivamento](#archiving-configuration)

## <a name="call-detail-recording"></a>Registro de Detalhes de Chamada

**O** submenu DE GRAVAÇÃO DE DETALHES DA CHAMADA permite que os administradores gerenciem as configurações de CDR (registro de detalhes de chamada). A CDR permite rastrear o uso de coisas como sessões de mensagens instantâneas ponto a ponto, chamadas telefônicas VoIP (Protocolo de Voz sobre Internet) e chamadas de conferência.

Vamos considerar as várias tarefas que um usuário pode realizar no **REGISTRO** DE DETALHES da CHAMADA e os cmdlets Skype for Business essas tarefas são mapeados.

---

> **Cenário 1**: listar todas as configurações de CDR

   ![Listar Configuração de Cdr](./media/cdr-configurations-1.png)

***Cmdlet***

[Get-CsCdrConfiguration](/powershell/module/skype/get-cscdrconfiguration)

***Exemplo***

```powershell
 Get-CsCdrConfiguration
```

---

> **Cenário 2**: Criar uma nova configuração de CDR

   ![Criar Configuração de Cdr](./media/cdr-configurations-2.png)

***Cmdlet***

[New-CsCdrConfiguration](/powershell/module/skype/new-cscdrconfiguration)  

***Exemplo***

```powershell
 New-CsCdrConfiguration -Identity site:Redmond -EnableCDR $False
```

---

> **Cenário 3**: Obter detalhes de uma configuração de CDR escolhida

   ![Obter Configuração de Cdr](./media/cdr-configurations-3.png)

***Cmdlet***

[Get-CsCdrConfiguration](/powershell/module/skype/get-cscdrconfiguration)

***Exemplo***

```powershell
 Get-CsCdrConfiguration -Identity site:Redmond
```

---

> **Cenário 4**: Excluir configurações de CDR escolhidas

   ![Excluir Configuração de Cdr](./media/cdr-configurations-4.png)

***Cmdlet***

[Remove-CsCdrConfiguration](/powershell/module/skype/remove-cscdrconfiguration)

***Exemplo***

```powershell
 Remove-CsCdrConfiguration -Identity site:Redmond
```

---

> **Cenário 5**: Atualizar uma configuração de CDR

   ![Atualizar Configuração do Cdr](./media/cdr-configurations-5.png)

***Cmdlet***

[Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration)

***Exemplo***

```powershell
 Set-CsCdrConfiguration -Identity site:Redmond -PurgeHourOfDay 23
```

---

## <a name="quality-of-experience-data"></a>Qualidade dos dados da experiência

O sub menu **DADOS DE QUALIDADE** DA EXPERIÊNCIA permite que os administradores gerenciem as configurações de QoE (Qualidade da Experiência). em toda a organização; isso inclui o gerenciamento de expansão de grupo, configurações de certificado e métodos de autenticação permitidos. Como os administradores podem configurar configurações diferentes no escopo global, de site e de serviço (embora para o único serviço de Serviços Web), é possível personalizar os recursos dos Serviços Web para diferentes usuários e locais diferentes.

Considere as várias tarefas que um usuário pode realizar no **WEB SERVICE** e os cmdlets Skype for Business essas tarefas são mapeados.

---
> **Cenário 1**: listar todas as configurações de QoE

   ![Listar configuração de QoE](./media/qoe-configuration-1.png)

***Cmdlet***

[Get-CsQoEConfiguration](/powershell/module/skype/get-csqoeconfiguration)

***Exemplo***

```powershell
 Get-CsQoEConfiguration
```

---

> **Cenário 2**: Criar uma nova configuração de QoE

   ![Nova configuração de QoE](./media/qoe-configuration-2.png)

***Cmdlet***

[New-CsQoEConfiguration](/powershell/module/skype/new-csqoeconfiguration)  

***Exemplo***

```powershell
 New-CsQoEConfiguration -Identity site:Redmond -EnableQoE $False
```

---

> **Cenário 3**: Obter detalhes de uma configuração de QoE escolhida

   ![Obter configuração de QoE](./media/qoe-configuration-3.png)

***Cmdlet***

[Get-CsQoEConfiguration](/powershell/module/skype/get-csqoeconfiguration)

***Exemplo***

```powershell
 Get-CsQoEConfiguration -Identity site:Redmond
```

---

> **Cenário 4**: Excluir configurações de QoE escolhidas

   ![Excluir configuração de QoE](./media/qoe-configuration-4.png)

***Cmdlet***

[Remove-CsQoEConfiguration](/powershell/module/skype/remove-csqoeconfiguration)

***Exemplo***

```powershell
 Remove-CsQoEConfiguration -Identity site:Redmond
```

---

> **Cenário 5**: Atualizar uma configuração de QoE

   ![Atualizar a configuração de QoE](./media/qoe-configuration-5.png)

***Cmdlet***

[Set-CsQoEConfiguration](/powershell/module/skype/set-csqoeconfiguration)

***Exemplo***

```powershell
 Set-CsQoEConfiguration -Identity site:Redmond -EnableQoE $False
```

---

## <a name="archiving-policy"></a>Política de Arquivamento

Os administradores podem usar **a POLÍTICA DE ARQUIVAMENTO para** gerenciar políticas de arquivamento de sessão de mensagens instantâneas (IM). As políticas de arquivamento permitem que você arquive todas as sessões de IM e webconferência que ocorrem entre usuários internos e/ou entre usuários internos e usuários externos

Considere as várias tarefas que um usuário pode realizar na **POLÍTICA** de ARQUIVAMENTO e os cmdlets Skype for Business essas tarefas são mapeados.

---

> **Cenário 1**: Listar todas as políticas de arquivamento

   ![Política de Arquivamento de Lista](./media/archiving-policy-1.png)

***Cmdlet***

[Get-CsArchivingPolicy](/powershell/module/skype/get-csarchivingpolicy)

***Exemplo***

```powershell
 Get-CsArchivingPolicy
```

---

> **Cenário 2**: Criar uma nova política de arquivamento

   ![Criar Política de Arquivamento](./media/archiving-policy-2.png)

***Cmdlet***

[New-CsArchivingPolicy](/powershell/module/skype/new-csarchivingpolicy)  

***Exemplo***

```powershell
 New-CsArchivingPolicy -Identity site:Redmond -ArchiveInternal $True
```

---

> **Cenário 3**: Obter detalhes de uma política de arquivamento escolhida

   ![Obter Política de Arquivamento](./media/archiving-policy-3.png)

***Cmdlet***

[Get-CsArchivingPolicy](/powershell/module/skype/get-csarchivingpolicy)

***Exemplo***

```powershell
 Get-CsArchivingPolicy -Identity site:Redmond
```

---

> **Cenário 4**: Excluir políticas de arquivamento escolhidas

   ![Excluir Política de Arquivamento](./media/archiving-policy-4.png)

***Cmdlet***

[Remove-CsArchivingPolicy](/powershell/module/skype/remove-csarchivingpolicy)

***Exemplo***

```powershell
 Remove-CsArchivingPolicy -Identity site:Redmond
```

---

> **Cenário 5**: Atualizar uma política de arquivamento

   ![Atualizar Política de Arquivamento](./media/archiving-policy-5.png)

***Cmdlet***

[Set-CsArchivingPolicy](/powershell/module/skype/set-csarchivingpolicy)

***Exemplo***

```powershell
 Set-CsArchivingPolicy -Identity global -ArchiveInternal $True
```

---

## <a name="archiving-configuration"></a>Configuração de Arquivamento

Os administradores podem usar **a CONFIGURAÇÃO DE** ARQUIVAMENTO para configurar como (ou se) sessões de mensagens instantâneas (IM) são arquivadas na organização.

Vamos considerar as várias tarefas que um usuário pode realizar na CONFIGURAÇÃO DE ARQUIVAMENTO **e** os cmdlets Skype for Business essas tarefas são mapeados.

---

> **Cenário 1**: Listar todas as configurações de arquivamento

   ![Configuração de Arquivamento de Lista](./media/archiving-configuration-1.png)

***Cmdlet***

[Get-CsArchivingConfiguration](/powershell/module/skype/get-csarchivingconfiguration)

***Exemplo***

```powershell
 Get-CsArchivingConfiguration
```

---

> **Cenário 2**: Criar uma nova configuração de arquivamento

   ![Criar Configuração de Arquivamento](./media/archiving-configuration-2.png)

***Cmdlet***

[New-CsArchivingConfiguration](/powershell/module/skype/new-csarchivingconfiguration)  

***Exemplo***

```powershell
 New-CsArchivingConfiguration -Identity site:Redmond -EnableArchiving "ImOnly"
```

---

> **Cenário 3**: Obter detalhes de uma configuração de arquivamento escolhida

   ![Obter Configuração de Arquivamento](./media/archiving-configuration-3.png)

***Cmdlet***

[Get-CsArchivingConfiguration](/powershell/module/skype/get-csarchivingconfiguration)

***Exemplo***

```powershell
 Get-CsArchivingConfiguration -Identity site:Redmond
```

---

> **Cenário 4**: Excluir configurações de arquivamento escolhidas

   ![Excluir Configuração de Arquivamento](./media/archiving-configuration-4.png)

***Cmdlet***

[Remove-CsArchivingConfiguration](/powershell/module/skype/remove-csarchivingconfiguration)

***Exemplo***

```powershell
 Remove-CsArchivingConfiguration -Identity site:Redmond
```

---

> **Cenário 5**: Atualizar uma configuração de arquivamento

   ![Atualizar Configuração de Arquivamento](./media/archiving-configuration-5.png)

***Cmdlet***

[Set-CsArchivingConfiguration](/powershell/module/skype/set-csarchivingconfiguration)

***Exemplo***

```powershell
 Set-CsArchivingConfiguration -Identity site:Redmond -ArchiveDuplicateMessages $False -KeepArchivingDataForDays 30
```

---

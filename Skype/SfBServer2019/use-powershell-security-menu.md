---
title: Usar o PowerShell para tarefas no menu Segurança
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
description: 'Resumo: Skype for Business Server painel de controle para o menu Mapeamento de Cmdlet para Segurança.'
ms.openlocfilehash: 6e726b13b9428b213011126abf5ac0869e6cfbf8
ms.sourcegitcommit: eba9fc680233e9e03773a2942f22afe6247eec41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60824870"
---
# <a name="security"></a>Segurança

Este artigo descreve como resultados semelhantes aos do **item** de menu Segurança no Painel de Controle herdado podem ser obtidos usando cmdlets.

Este artigo descreve os seguintes sub-menus:

- [Segurança](#security)
  - [Registrador](#registrar)
  - [Serviço Web](#web-service)
  - [Política de PIN](#pin-policy)

## <a name="registrar"></a>Registrador

**O** sub-menu REGISTRADOR permite que os administradores gerenciem servidores proxy por meio das configurações do servidor proxy. Essas configurações, que podem ser aplicadas no escopo global e no escopo do serviço (embora apenas para os serviços de Servidor de Borda e Registrador) permitem controlar coisas como os protocolos de autenticação que podem ser usados pelos pontos de extremidade do cliente e se a compactação será ou não usada em conexões de servidor proxy de entrada e saída.

Considere as várias tarefas que um usuário pode realizar no **REGISTRADOR** e os cmdlets Skype for Business essas tarefas são mapeados.

---

> **Cenário 1**: Listar todas as configurações de proxy

   ![Configuração de Proxy de Lista](./media/proxy-configurations-1.png)

***Cmdlet***

[Get-CsProxyConfiguration](/powershell/module/skype/get-csproxyconfiguration)

***Exemplo***

```powershell
 Get-CsProxyConfiguration
```

---

> **Cenário 2**: Criar uma nova configuração de proxy

   ![Criar Configuração de Proxy](./media/proxy-configurations-2.png)

***Cmdlet***

[New-CsProxyConfiguration](/powershell/module/skype/new-csproxyconfiguration)  

***Exemplo***

```powershell
 New-CsProxyConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com" -RequestServerCompression $True -MaxClientMessageBodySizeKb 256
```

---

> **Cenário 3**: Obter detalhes de uma configuração de proxy escolhida

   ![Obter Configuração de Proxy](./media/proxy-configurations-3.png)

***Cmdlet***

[Get-CsProxyConfiguration](/powershell/module/skype/get-csproxyconfiguration)

***Exemplo***

```powershell
 Get-CsProxyConfiguration -Identity "service:EdgeServer:atl-cs-001.litwareinc.com"
```

---

> **Cenário 4**: Excluir configurações de proxy escolhidas

   ![Excluir Configuração de Proxy](./media/proxy-configurations-4.png)

***Cmdlet***

[Remove-CsProxyConfiguration](/powershell/module/skype/remove-csproxyconfiguration)

***Exemplo***

```powershell
 Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com
```

---

> **Cenário 5**: Atualizar uma configuração de proxy

   ![Atualizar Configuração de Proxy](./media/proxy-configurations-5.png)

***Cmdlet***

[Set-CsProxyConfiguration](/powershell/module/skype/set-csproxyconfiguration)

***Exemplo***

```powershell
 Set-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-001.litwareinc.com -AcceptServerCompression $True
```

---

## <a name="web-service"></a>Serviço Web

O item de sub-menu DO WEB **SERVICE** em **Segurança** permite que os administradores gerenciem as configurações dos Serviços Web em toda a organização; isso inclui o gerenciamento de expansão de grupo, configurações de certificado e métodos de autenticação permitidos. Como os administradores podem configurar configurações diferentes no escopo global, de site e de serviço (embora para o único serviço de Serviços Web), é possível personalizar os recursos dos Serviços Web para diferentes usuários e locais diferentes.

Considere as várias tarefas que um usuário pode realizar no **WEB SERVICE** e os cmdlets Skype for Business essas tarefas são mapeados.

---
> **Cenário 1**: Listar todas as configurações do serviço Web

   ![Listar configuração do serviço Web](./media/web-service-1.png)

***Cmdlet***

[Get-CsWebServiceConfiguration](/powershell/module/skype/get-cswebserviceconfiguration)

***Exemplo***

```powershell
 Get-CsWebServiceConfiguration
```

---

> **Cenário 2**: Criar uma nova configuração de serviço Web

   ![Nova configuração do serviço Web](./media/web-service-2.png)

***Cmdlet***

[New-CsWebServiceConfiguration](/powershell/module/skype/new-cswebserviceconfiguration)  

***Exemplo***

```powershell
 New-CsWebServiceConfiguration -Identity site:Redmond -EnableGroupExpansion $False -UseCertificateAuth $True
```

---

> **Cenário 3**: Obter detalhes de uma configuração de serviço Web escolhida

   ![Obter configuração do serviço Web](./media/web-service-3.png)

***Cmdlet***

[Get-CsWebServiceConfiguration](/powershell/module/skype/get-cswebserviceconfiguration)

***Exemplo***

```powershell
 Get-CsWebServiceConfiguration -Identity site:Redmond
```

---

> **Cenário 4**: Excluir configurações de serviço Web escolhidas

   ![Excluir configuração do serviço Web](./media/web-service-4.png)

***Cmdlet***

[Remove-CsWebServiceConfiguration](/powershell/module/skype/remove-cswebserviceconfiguration)

***Exemplo***

```powershell
 Remove-CsWebServiceConfiguration -Identity site:Redmond
```

---

> **Cenário 5**: Atualizar uma configuração de serviço Web

   ![Atualizar configuração do serviço Web](./media/Web-service-5.png)

***Cmdlet***

[Set-CsWebServiceConfiguration](/powershell/module/skype/set-cswebserviceconfiguration)

***Exemplo***

```powershell
 Set-CsWebServiceConfiguration -Identity site:Redmond -EnableGroupExpansion $True
```

---

## <a name="pin-policy"></a>Política de PIN

Os administradores podem usar **a POLÍTICA de PIN** para gerenciar propriedades de autenticação de PIN; por exemplo, pode-se especificar o comprimento mínimo para um PIN e determinar se um permitirá PINs que usam "padrões comuns" como dígitos consecutivos (por exemplo, um PIN como 123456)

Considere as várias tarefas que um usuário pode realizar na POLÍTICA de **PIN** e os cmdlets Skype for Business essas tarefas são mapeados.

---

> **Cenário 1**: listar todas as políticas de PIN

   ![Política de Pin de Lista](./media/pin-policy-1.png)

***Cmdlet***

[Get-CsPinPolicy](/powershell/module/skype/get-cspinpolicy)

***Exemplo***

```powershell
 Get-CsPinPolicy
```

---

> **Cenário 2**: Criar uma nova política de PIN

   ![Criar Política de Pin](./media/pin-policy-2.png)

***Cmdlet***

[New-CsPinPolicy](/powershell/module/skype/new-cspinpolicy)  

***Exemplo***

```powershell
 New-CsPinPolicy -Identity "site:Redmond" -MinPasswordLength 10
```

---

> **Cenário 3**: Obter detalhes de uma Política de PIN escolhida

   ![Obter Política de PIN](./media/pin-policy-3.png)

***Cmdlet***

[Get-CsPinPolicy](/powershell/module/skype/get-cspinpolicy)

***Exemplo***

```powershell
 Get-CsPinPolicy -Identity "site:Redmond"
```

---

> **Cenário 4**: Excluir políticas de PIN escolhidas

   ![Excluir Política de PIN](./media/pin-policy-4.png)

***Cmdlet***

[Remove-CsPinPolicy](/powershell/module/skype/remove-cspinpolicy)

***Exemplo***

```powershell
 Remove-CsPinPolicy -Identity RedmondUsersPinPolicy
```

---

> **Cenário 5**: atualizar uma política de PIN

   ![Atualizar Política de PIN](./media/pin-policy-5.png)

***Cmdlet***

[Set-CsPinPolicy](/powershell/module/skype/set-cspinpolicy)

***Exemplo***

```powershell
 Set-CsPinPolicy -Identity site:Redmond -MinPasswordLength 10
```

---

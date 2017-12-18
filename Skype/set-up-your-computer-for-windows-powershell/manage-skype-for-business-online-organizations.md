---
title: "Gerenciar o Skype for Business Online organizações que usam o Skype para Business Connector Online"
ms.author: tonysmit
author: tonysmit
ms.date: 5/17/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.assetid: c71f0d4d-5b6b-40ac-bc4a-6b97c05a121a
description: "Use Windows PowerShell and the Get-CsTenant and Get-CsTenantLicensingConfiguration cmdlets to get information about your Skype for Business Online tenant."
---

# Gerenciar o Skype for Business Online organizações que usam o Skype para Business Connector Online

> [!IMPORTANT]
> Este artigo foi traduzido por um sistema de tradução automática, leia o aviso de isenção de responsabilidade.  
  
Você pode encontrar informações sobre seu locatário Skype for Business Online usando os cmdlets **Get-CsTenant** e **Get-CsTenantLicensingConfiguration**.
  
## Gerenciar o Skype for Business Online locatários

Para retornar informações sobre seu locatário Skype for Business Online, ligue para o cmdlet [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) sem parâmetros adicionais.
  
```
Get-CsTenant
```

Para retornar apenas o locatário nome e ID, use este comando.
  
```
Get-CsTenant | Select-Object Name, TenantID
```

O valor do parâmetro  _TenantID_ é necessário ao executar cmdlets como[Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) e[Set-CsTenantFederationConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849602).
  
Para localizar informações sobre informações de licenciamento do locatário especificado estão disponíveis no Centro de administração Skype for Business Online, use o cmdlet [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) .
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Aviso de Isenção de Tradução Automática**: Este artigo foi traduzido por computador, sem intervenção humana. A Microsoft oferece essas traduções automáticas para ajudar as pessoas que não falam inglês a aproveitar os textos escritos sobre produtos, serviços e tecnologias da Microsoft. Como este artigo foi traduzido automaticamente, é possível que contenha erros de vocabulário, sintaxe ou gramática. 
  


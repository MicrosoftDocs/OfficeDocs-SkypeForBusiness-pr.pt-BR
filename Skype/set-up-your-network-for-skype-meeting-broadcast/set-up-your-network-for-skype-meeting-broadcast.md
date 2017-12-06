---
title: "Configurar a rede para a Transmissão de Reunião do Skype"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/16/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_Skype4B_Online
- Adm_Skype4B_Online_Top
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
ms.assetid: dfa736b9-4920-4f48-b8c0-b5487ec6086f
description: "Learn about the Skype Meeting Broadcast feature of Skype for Business Online that enables you to schedule, produce, and broadcast meetings or events to large online audiences up to 10,000 attendees."
---

# Configurar a rede para a Transmissão de Reunião do Skype

> [!IMPORTANT]
> Este artigo foi traduzido por um sistema de tradução automática, leia o [aviso de isenção de responsabilidade](dfa736b9-4920-4f48-b8c0-b5487ec6086f.md#MT_Footer). Para sua referência, veja a versão em inglês deste artigo [aqui](https://support.office.com/en-us/article/dfa736b9-4920-4f48-b8c0-b5487ec6086f). 
  
Após [Habilitar a Transmissão de Reunião do Skype](enable-skype-meeting-broadcast.md) a Transmissão de Reunião do Skype, você precisa configurar a rede. Siga esta etapa se quiser realizar webinars ou outras transmissões para pessoas de fora de sua empresa.
  
Se você não tiver experiência com a configuração do firewall, considere contratar um [Parceiro Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) para realizar essa etapa para você.
  
Para ignorar esta etapa e em vez disso, adicione outro business sua federação, para que você possa convidá-los a transmissões, siga as etapas em [Permitir que os usuários entrem em contato com usuários externos do Skype for Business](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).
  
## Etapa 1: configurar domínios permitidos

Use **um** dos seguintes métodos para configurar os domínios permitidos:
  
### 

 **Método 1: Usar o Centro de administração do Office 365**
  
1. Vá até o **Centro de administração do Office 365** e, em seguida, no painel de navegação esquerdo, clique em **configurações** > **suplementos e serviços** e escolha **Skype for Business**.
    
2. Na página **compartilhamento externo** em **exceções de domínio**, selecione **todos os domínios são bloqueados, exceto** e insira os seguintes domínios separados por vírgulas (,):
    
  - noammeetings.lync.com
    
  - emeameetings.lync.com
    
  - apacmeetings.lync.com
    
  - resources.lync.com
    
3. Clique em **Salvar**.
    
### 

 **Método 2: Usar o Windows PowerShell**
  
- No **Menu Iniciar**, clique com botão direito **Do Windows PowerShell** e clique em **Executar como administrador**. Na janela do **Windows PowerShell**, digitar cada linha e pressione Enter.
    
  ```
  $r = New-CsEdgeDomainPattern -Domain "noammeetings.lync.com"
  ```

  ```
  $s = New-CsEdgeDomainPattern -Domain "emeameetings.lync.com"
  ```

  ```
  $t = New-CsEdgeDomainPattern -Domain "apacmeetings.lync.com"
  ```

  ```
  $n = New-CsEdgeDomainPattern -Domain "resources.lync.com"
  ```

  ```
  $newAllowList = New-CsEdgeAllowList -AllowedDomain $r,$s,$t,$n
  ```

  ```
  Set-CsTenantFederationConfiguration -AllowedDomains $newAllowList
  ```

## Etapa 2: Adicionar domínios, URLs e IP transmissão de reunião do Skype endereços

A segunda etapa no processo de instalação é para você primeiro adicionar domínios que são necessários e, em seguida, adicione endereços IP e URLs que são necessários para transmissão de reunião do Skype trabalhar.
  
- **Adicione os pontos de extremidade do domínio necessário:**
    
    Para usar a Transmissão de Reunião do Skype, os seguintes pontos de extremidade devem estar acessíveis para os computadores cliente.
    
|
|
|**Linha**|**Finalidade**|**Fonte | Credenciais**|**Destino**|**ExpressRoute para comunidades BGP do Office 365**|**Endereço CIDR**|**Porta**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1  <br/> |**Obrigatório:** Pontos de extremidade do Skype for Business. <br/> |confira o [Skype for Business Online](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_LYO) e confirme se todas as entradas rotuladas como "obrigatório" estão acessíveis. <br/> ||||
|2  <br/> |**Obrigatório:** apresentador e participante da[Transmissão de Reunião do Skype](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d) <br/> |computador cliente/usuário conectado  <br/> |
```
*.broadcast.skype.com
broadcast.skype.com
browser.pipe.aria.microsoft.com

```

|sim  <br/> |[](8548a211-3fe7-47cb-abb1-355ea5aa88a2.md#BKMK_SfB_IP).  <br/> |TCP 443  <br/> |
|3  <br/> |**Obrigatório:** apresentador e participante da[Transmissão de Reunião do Skype](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d) <br/> |computador cliente/usuário conectado  <br/> |
```
aka.ms
amp.azure.net

```

|não  <br/> |N/D  <br/> |TCP 443  <br/> |
|4  <br/> |**Obrigatório:** apresentador e participante (inclusive CDNs) da[Transmissão de Reunião do Skype](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d) <br/> |computador cliente/usuário conectado  <br/> |
```
*.keydelivery.mediaservices.windows.net
*.msecnd.net
*.streaming.mediaservices.windows.net
ajax.aspnetcdn.com
mlccdn.blob.core.windows.net

```

|não  <br/> |N/D  <br/> |TCP 443  <br/> |
   
- **Adicionar o Skype necessário para Business Online URLs de ponto de extremidade e endereços IP verificando quais são necessários**[aqui](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).
    
## Configurar a Transmissão de Reunião do Skype em implantações e organizações híbridas

Se você tiver uma organização Skype for Business Online e uma implantação local do Lync Server 2010, Microsoft Lync Server 2013 e Skype for Business Server 2015 e os usuários online e local, há outras etapas de instalação que você precisará fazer além àquelas acima para habilitar sua organização local para se comunicar com Skype for Business Online e permitir que todos os seus usuários possam criar e participar de uma Transmissão de Reunião do Skype. Para ver o que são esses requisitos, consulte [configurar sua implantação local para transmissão de reunião do Skype](https://go.microsoft.com/fwlink/?LinkId=617070).
  
## Tópicos Relacionados

[Habilitar a Transmissão de Reunião do Skype](enable-skype-meeting-broadcast.md)
  
[URLs e intervalos de endereços IP do Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Configurar o Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Aviso de Isenção de Tradução Automática**: Este artigo foi traduzido por computador, sem intervenção humana. A Microsoft oferece essas traduções automáticas para ajudar as pessoas que não falam inglês a aproveitar os textos escritos sobre produtos, serviços e tecnologias da Microsoft. Como este artigo foi traduzido automaticamente, é possível que contenha erros de vocabulário, sintaxe ou gramática. 
  


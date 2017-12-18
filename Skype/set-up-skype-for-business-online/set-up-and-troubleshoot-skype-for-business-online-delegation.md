---
title: "Configurar e solucionar problemas Skype for Business Online delegação"
ms.author: tonysmit
author: tonysmit
ms.date: 11/23/2017
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: e676b911-5f82-41d8-b4ce-3d0d45c3cd04
description: "Este artigo explica como configurar e solucionar problemas Skype for Business Online delegação. Este artigo fornece orientação para recomendações de configuração, práticas recomendadas e as etapas de solução de problemas."
---

# Configurar e solucionar problemas Skype for Business Online delegação

> [!IMPORTANT]
> Este artigo foi traduzido por um sistema de tradução automática, leia o aviso de isenção de responsabilidade.  
  
Este artigo explica como configurar e solucionar problemas Skype for Business Online delegação. Este artigo fornece orientação para recomendações de configuração, práticas recomendadas e as etapas de solução de problemas.
  
## Requisitos e diretrizes

### Diretrizes para delegação

Configurar e Obtendo delegação funcione corretamente dependem você seguindo estas diretrizes:
  
- Você deve estar usando o Skype for Business 2015 completa do cliente com as últimas atualizações ou o Skype para Business 2016 completa do cliente.
    
- Você deve estar usando o cliente do Outlook 2013 com as últimas atualizações ou Outlook 2016.
    
- Certifique-se de que os computadores de representante e delegante tem um perfil de email do Outlook que é o principal ou o perfil padrão. Esse perfil de email deve conter apenas uma conta.
    
- Skype for Business para delegante e o representante deve ser usuários Online. Além disso, as Exchange Server caixas de correio para cada conta deve estar Online ou ambos ser local.
    
- Delegante tanto o representante devem estar usando a mesma versão principal do Outlook.
    
- O valor do atributo **EnableExchangeDelegateSync** deve ser definido como **true** na diretiva do cliente. Você pode verificar essa configuração executando o cmdlet **Get-CSClientPolicy** no Skype for Business Online PowerShell módulo.
    
- Delegante tanto o representante devem estar conectados ao Skype for Business e Outlook ao mesmo tempo em estações de trabalho diferentes.
    
- Caixas de correio compartilhadas não são suportadas para Skype for Business Online delegação. Isso ocorre porque a caixa de correio compartilhada não tem a lista de controle de acesso (ACL) **sendonbehalf**.
    
### Skype para o suporte de versão do cliente de negócios

||**Outlook 2013**|**Outlook 2016**|
|:-----|:-----|:-----|
|**Lync/Skype para Business básicos do cliente**|
|:-----|
|**Skype for Business 2015**|
|:-----|
|**Skype for Business 2016**|
|:-----|
   
### Requisitos de licenciamento

**Cenário de licenciamento do Enterprise E3**

|****Licença****|****Clientes****|****Observações****|
|:-----|:-----|:-----|
|Enterprise E3  <br/> |Lync 2013 (Skype for Business 2015) usado com o Outlook 2013 ou Outlook 2016  <br/> Skype para Business 2016 usado com o Outlook 2013 ou Outlook 2016  <br/> |Skype for Business básicos do cliente não dá suporte a delegação.  <br/> Para clientes do Mac, você pode delegar chamadas, mas não em reuniões.  <br/> |
|Enterprise E3 com sistema de telefone do Office 365 + xCalling do Office 365 plano  <br/> |Lync 2013 (Skype for Business 2015) usado com o Outlook 2013 ou Outlook 2016  <br/> Skype para Business 2016 usado com o Outlook 2013 ou Outlook 2016  <br/> Lync para Mac 2011  <br/> |Skype for Business básicos do cliente não dá suporte a delegação.  <br/> Para clientes do Mac, você pode delegar chamadas, mas não em reuniões.  <br/> |
   
**Cenário de licenciamento E5 Enterprise**

|****Licença****|****Clientes****|****Observações****|
|:-----|:-----|:-----|
|Enterprise E5  <br/> |Lync 2013 (Skype for Business 2015) usado com o Outlook 2013 ou Outlook 2016.  <br/> Skype para Business 2016 usado com o Outlook 2013 ou Outlook 2016  <br/> |Skype for Business básicos do cliente não dá suporte a delegação.  <br/> Para clientes do Mac, você pode delegar chamadas, mas não em reuniões.  <br/> |
|E5 Enterprise plus o plano de chamada do Office 365  <br/> |Skype for Business para Mac 2016  <br/> Lync 2013 (Skype for Business 2015) usado com o Outlook 2013 ou Outlook 2016  <br/> Skype para Business 2016 usado com o Outlook 2013 ou Outlook 2016  <br/> Lync para Mac 2011  <br/> |Skype for Business básicos do cliente não dá suporte a delegação.  <br/> Para clientes do Mac, você pode delegar chamadas, mas não em reuniões.  <br/> |
   
## Configurar e verificar a delegação

Para configurar o Skype for Business Online delegação, siga estas etapas:
  
### Para clientes Windows

 **Guia de encaminhamento de chamadas**
  
1. Selecione **Ferramentas** > **Opções** > **configurações de encaminhamento de chamadas**.
    
2. Selecione **Editar membros de meus representantes**.
    
3. Selecione **Adicionar**, selecione o representante que você deseja adicionar e selecione **Okey**.
    
 **Guia não encaminhar chamadas**
  
1. No Outlook, selecione **arquivo** > **Configurações de conta** > **Acesso de representante** > **Adicionar**.
    
2. Localize e adicione o nome da pessoa que vai será o representante.
    
3. Selecione o menu **calendário** e selecione **Editor (pode ler, criar e modificar itens)**.
    
### Para clientes de Mac - Lync

 **Guia de encaminhamento de chamadas**
  
- Se o cliente não tem uma guia de **Encaminhamento de chamadas** com o link **Editar membros de meus representantes** e delegante está localizado em um computador Mac, delegante deve entrar um computador baseado no Windows para configurar a delegação. Isso ocorre porque os clientes de Mac não é possível fazer conexões MAPI e esse é um requisito para estabelecer o Skype para delegação de negócios do Outlook.
    
### Verificar o sucesso

Se a instalação for bem-sucedida, o representante deve ver o que **você foi adicionado como um representante para < nome >** mensagem e também que o grupo de **pessoas para as quais gerenciar chamadas** é criado. Delegante deverá ver que o grupo **delegados** é criado.
  
> [!NOTE]
> Permissões de delegação normalmente aparecem em 30 minutos do processo de instalação. No entanto, esse processo pode levar até 24 horas para ser concluída. 
  
## Solução de problemas

### Problemas comuns

> **Problema 1** A entrada de representante continua a aparecer no grupo de **pessoas para as quais gerenciar chamadas** após delegante removeu o representante do cliente do Outlook.
    
    **Resolução 1** Sobre o Skype for Business client, o representante no grupo **representantes** de atalho e selecione **Remover do grupo**.
    
> **Problema 2** Depois de acesso de representante é concedido por meio do cliente do Outlook, a mensagem de confirmação nem o grupo de **pessoas para as quais gerenciar chamadas** exibido para o representante.
    
    **Resolução 2** Remover a delegação de cliente do Outlook, aguarde cerca de 15 minutos para replicação e adicione novamente o representante.
    
### Outros problemas comuns

- Delegação não funciona se for excedido o limite dos 25 delegantes e 25 delegados.
    
- O Skype for Business básicos do cliente não é compatíveis.
    
    > [!NOTE]
    > Se você instalar o Skype for Business básicos do cliente, ele removerá e quebrar delegação. 
  
- Se o valor de **Status de MAPI** não **Okey**, certifique-se de que os valores de **SIP** e **SMTP** compatível.
    
    > [!NOTE]
    > Pode levar alguns minutos para que o status MAPI para exibir como **Okey** após iniciar o Skype for Business e o Outlook pela primeira vez.
  
- Criando um grupo de segurança e adicionando permissões de delegação para esse grupo de segurança não são compatíveis.
    
- MAPI não está disponível. Consulte [erro "MAPI disponível" no Skype para Business 2016 cliente](https://support.microsoft.com/en-us/help/3147130).
    
- A caixa de correio do Exchange Online não puder ser acessada por meio do Skype for Business client. Nesse caso, execute o [teste de conectividade do Outlook](https://testconnectivity.microsoft.com/) para certificar-se de que ele passa.
    
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Aviso de Isenção de Tradução Automática**: Este artigo foi traduzido por computador, sem intervenção humana. A Microsoft oferece essas traduções automáticas para ajudar as pessoas que não falam inglês a aproveitar os textos escritos sobre produtos, serviços e tecnologias da Microsoft. Como este artigo foi traduzido automaticamente, é possível que contenha erros de vocabulário, sintaxe ou gramática. 
  


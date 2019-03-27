---
title: Configurar os computadores que serão monitorados no Skype for Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 11/7/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Resumo: Instalar os arquivos de agente do Operations Manager no Skype para Business Server 2019 computador a serem monitorados e configure o computador para atuar como um proxy do System Center.'
ms.openlocfilehash: 90608d9233bea466b523418553d5421735234aee
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30875415"
---
# <a name="configure-the-skype-for-business-server-computers-that-will-be-monitored"></a>Configurar os computadores que serão monitorados no Skype for Business Server

**Resumo:** Instale os arquivos de agente do Operations Manager no Skype para Business Server 2019 computador a serem monitorados e configure o computador para atuar como um proxy do System Center.

Cada Skype para Business Server 2019 computador que você deseja monitorar deve ser capaz de autorelatar sua existência para o servidor de gerenciamento. Para habilitar esse processo, você deve instalar os arquivos de agente do Operations Manager em todos os computadores a serem monitorados. Após a instalação dos arquivos de agente, você deve configurar o computador para atuar como um proxy do System Center. Certifique-se de que você primeiro instalado e configurado Skype para Business Server nesses computadores antes de executar estes procedimentos.

## <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network"></a>Instalando um Certificado no Nó Inspetor Localizado Fora da Rede do Perímetro
<a name="watcher_node_outside"> </a>

Agentes do System Center Operations Manager executando em um perímetro de rede (por exemplo, um Skype para servidor de borda do servidor de negócios), fora da empresa (por exemplo, um nó do Inspetor de transação sintética externo) ou em uma relação de confiança do Active Directory podem exigir a limites, a configuração de um servidor de Gateway do System Center Operations Manager. Essa função de servidor permite que os agentes que não tenham uma relação de confiança com o Servidor de Gerenciamento Raiz gerem alertas. Para obter detalhes, consulte [Gerenciando servidores de Gateway do Operations Manager 2012](https://technet.microsoft.com/en-us/library/hh212823.aspx).

Se você implantar um agente em um desses locais, você também precisará solicitar e configurar um certificado que permite que o nó do Inspetor enviar alertas para o System Center Operations Manager. Para simplificar esse processo, a equipe do Operations Manager criou um conjunto de utilitários que permitem que você solicitar e instalar o tipo de certificado correto no computador do nó do Inspetor. Para obter detalhes e para baixar esses utilitários, consulte [Obtendo certificados para fora do domínio ingressou agentes facilitados com o Assistente de geração de certificado](https://go.microsoft.com/fwlink/p/?LinkID=267421&amp;amp;clcid=0x409).

### <a name="installing-the-operation-manager-agent-files"></a>Instalando os arquivos de Agente do Operation Manager

1. Na sua mídia de configuração do System Center, clique duas vezes em **Setup.exe**.

2. No Assistente de instalação do System Center Operation Manager, clique em **Instalar o agente do Operations Manager**, de instalar o agente em instalações opcional

3. No Assistente de instalação do System Center, na bem-vindo à página do Assistente de instalação do System Center Operations Manager, clique em **Avançar**.

4. Na página pasta de destino, selecione a pasta onde os arquivos do agente do Gerenciador de operações serão instalados e clique em **Avançar**.

5. Na página Configuração do Grupo de Gerenciamento, selecione **Especificar a informação do grupo de gerenciamento** e clique em **Avançar**.

6. Na página Configuração do grupo de gerenciamento, digite o nome do seu grupo de gerenciamento do Operations Manager na caixa **Nome do grupo de gerenciamento** e, em seguida, digite o nome do host do servidor Operations Manager (por exemplo, atl-scom-001) em que o servidor de gerenciamento de ** **caixa. Se você alterou o número da porta usada pelo Operations Manager, digite o novo número da porta na caixa **Porta do Servidor de Gerenciamento**. Caso contrário, deixe a porta no valor padrão de 5723 e clique em **Avançar**.

7. Na página Conta de Ação do Agente, selecione **Sistema Local** e clique em **Avançar**.

8. Na página Microsoft Update, selecione **Eu não desejo usar o Microsoft Update** e clique em **Avançar**.

9. Na página **Pronto para instalar**, clique em Instalar.

10. Após a conclusão página do Assistente de instalação do System Center Operations Manager, clique em **Concluir**.

11. Clique em **Sair**.

Para o System Center 2012, você pode verificar que o agente foi criado por clicando em **Iniciar**, clicando em **Todos os programas**, clicando em **System Center Operations Manager 2012**e, em seguida, clicando em **Shell de 2012 do Operations Manager**. In the Operations Manager Shell, type the following Windows PowerShell command, and then press ENTER:
```
Get-SCOMAgent
```

Uma lista de todos os seus agentes do Operations Manager aparecerá.
## <a name="configuring-the-skype-for-business-server-computer-to-participate-in-system-center-discovery"></a>Configurando o computador com Skype for Business Server para participar da System Center Discovery
<a name="watcher_node_outside"> </a>

Para certificar-se de que seu novo Skype para agente Business Server participa do processo de descoberta para o System Center Operations Manager, você deve concluir o procedimento a seguir em cada computador onde o console do System Center Operations Manager foi instalado:

1. Na guia Administração, clique em **Agente Gerenciado**.

2. Clique em **Assistente de Descoberta** e conclua o assistente para o computador a ser descoberto.

3. Reinicie o serviço Agente de Integridade. A reinicialização do serviço forçará a descoberta do novo computador. Se você não reinicializar o serviço, pode levar desde que 4 horas antes da nova máquina é descoberta pela System Center Operations Manager.

4. Verifique se nenhum evento de erro foi registrado no log de eventos do Operations Manager.

5. No computador onde o agente é enviado com êxito será exibido na lista "Gerenciado por agente" e o computador no qual o agente foi instalado manualmente será mostrada em "Gerenciamento pendente", clique no nome do computador e aprovar.

6. Clique com o botão direito no nome do computador e clique em **Propriedades**. Na caixa de diálogo Propriedades, na guia Segurança, selecione **Permitir que este agente haja como um proxy e descubra objetos gerenciados em outros computadores** e clique em **OK**.



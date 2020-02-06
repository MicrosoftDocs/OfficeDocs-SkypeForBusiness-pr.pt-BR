---
title: Configurar os computadores que serão monitorados no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b24ea184-4b3e-4277-a244-157afb4b368b
description: 'Resumo: Instale os arquivos de agente do Operations Manager no computador do Skype for Business Server 2015 para ser monitorado e configure o computador para atuar como um proxy do System Center.'
ms.openlocfilehash: f5da9d309fd2353fbfd4009b825b731074c81fbb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816130"
---
# <a name="configure-the-skype-for-business-server-computers-that-will-be-monitored"></a>Configurar os computadores que serão monitorados no Skype for Business Server

**Resumo:** Instale os arquivos de agente do Operations Manager no computador do Skype for Business Server 2015 a ser monitorado e configure o computador para atuar como um proxy do System Center.

Cada computador com o Skype for Business Server 2015 que você deseja monitorar deve ser capaz de reportar sua existência ao servidor de gerenciamento. Para habilitar esse processo, você deve instalar os arquivos de agente do Operations Manager em todos os computadores a serem monitorados. Após a instalação dos arquivos de agente, você deve configurar o computador para atuar como um proxy do System Center. Verifique se você instalou e configurou primeiro o Skype for Business Server nesses computadores antes de executar esses procedimentos.

## <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network"></a>Instalando um Certificado no Nó Inspetor Localizado Fora da Rede do Perímetro
<a name="watcher_node_outside"> </a>

Agentes do System Center Operations Manager em execução em uma rede de perímetro (como um servidor de borda do Skype for Business Server), fora da empresa (como um nó de Inspetor de transação sintético) ou em um limite de confiança do Active Directory, podem exigir a configuração de um servidor de gateway do System Center Operations Manager. Essa função de servidor permite que os agentes que não tenham uma relação de confiança com o Servidor de Gerenciamento Raiz gerem alertas. Para obter detalhes, consulte [Gerenciando servidores de gateway no Operations Manager 2012](https://technet.microsoft.com/en-us/library/hh212823.aspx).

Se você implantar um agente em um desses locais, também será necessário solicitar e configurar um certificado que permita que o nó do Inspetor envie alertas para o System Center Operations Manager. Para simplificar esse processo, a equipe do Operations Manager criou um conjunto de utilitários que permitem que você solicite e instale o tipo correto de certificado no computador do nó do Inspetor. Para obter detalhes e baixar esses utilitários, consulte [obtendo certificados para agentes não associados a um domínio facilitados com o assistente de geração de certificados](https://go.microsoft.com/fwlink/p/?LinkID=267421&amp;amp;clcid=0x409).

### <a name="installing-the-operation-manager-agent-files"></a>Instalando os arquivos de Agente do Operation Manager

1. Na sua mídia de configuração do System Center, clique duas vezes em **Setup.exe**.

2. No assistente de configuração do System Center Operation Manager, clique em **instalar o agente do Operations Manager**, no agente de instalação em instalações opcionais

3. No assistente de configuração do System Center, na página Bem-vindo ao assistente de configuração do System Center Operations Manager, clique em **Avançar**.

4. Na página pasta de destino, selecione a pasta onde os arquivos de agente do Operations Manager serão instalados e clique em **Avançar**.

5. Na página Configuração do Grupo de Gerenciamento, selecione **Especificar a informação do grupo de gerenciamento** e clique em **Avançar**.

6. Na página configuração do grupo de gerenciamento, digite o nome do grupo de gerenciamento do Operations Manager na caixa **nome do grupo de gerenciamento** e digite o nome do host do servidor do Operations Manager (por exemplo, ATL-SCOM-001) na caixa servidor de **Gerenciamento** . Se você alterou o número da porta usada pelo Operations Manager, digite o novo número da porta na caixa **Porta do Servidor de Gerenciamento**. Caso contrário, deixe a porta no valor padrão de 5723 e clique em **Avançar**.

7. Na página Conta de Ação do Agente, selecione **Sistema Local** e clique em **Avançar**.

8. Na página Microsoft Update, selecione **Eu não desejo usar o Microsoft Update** e clique em **Avançar**.

9. Na página **Pronto para instalar**, clique em Instalar.

10. Na página Concluindo o assistente de configuração do System Center Operations Manager, clique em **concluir**.

11. Clique em **Sair**.

Para o System Center 2012, você pode verificar se o agente foi criado ao clicar em **Iniciar**, clicar em **todos os programas**, clicar em **System Center Operations Manager 2012**e, em seguida, clicar em **Shell de gerenciamento de operações do 2012**. In the Operations Manager Shell, type the following Windows PowerShell command, and then press ENTER:
```PowerShell
Get-SCOMAgent
```

Uma lista de todos os seus agentes do Operations Manager aparecerá.
## <a name="configuring-the-skype-for-business-server-computer-to-participate-in-system-center-discovery"></a>Configurando o computador com Skype for Business Server para participar da System Center Discovery
<a name="watcher_node_outside"> </a>

Para garantir que seu novo agente do Skype for Business participe do processo de descoberta do System Center Operations Manager, você deve concluir o procedimento a seguir em cada computador em que o console do System Center Operations Manager foi instalado:

1. Na guia Administração, clique em **Agente Gerenciado**.

2. Clique em **Assistente de Descoberta** e conclua o assistente para o computador a ser descoberto.

3. Reinicie o serviço Agente de Integridade. A reinicialização do serviço forçará a descoberta do novo computador. Se você não reinicializar o serviço, pode levar até 4 horas para que o novo computador seja descoberto pelo System Center Operations Manager.

4. Verifique se nenhum evento de erro foi registrado no log de eventos do Operations Manager.

5. O computador em que o agente foi enviado com êxito será mostrado na lista "gerenciado pelo agente" e o computador onde o agente foi instalado manualmente será mostrado em "gerenciamento pendente", clique no nome do computador e aprove.

6. Clique com o botão direito no nome do computador e clique em **Propriedades**. Na caixa de diálogo Propriedades, na guia Segurança, selecione **Permitir que este agente haja como um proxy e descubra objetos gerenciados em outros computadores** e clique em **OK**.



---
title: Mover dados do armazenamento de arquivos para um novo armazenamento de arquivos no Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8d1d5819-add2-4f5d-a436-74c00a281df0
description: 'Se você precisar remover o servidor de arquivos que está atuando como o armazenamento de arquivos para sua implantação do Skype for Business Server, ou se precisar fazer outras alterações que indisponíveis o armazenamento de arquivos atual, primeiro você precisará criar um novo compartilhamento. Em seguida, você precisa executar as seguintes etapas:'
ms.openlocfilehash: 606b3e1f405e75f58612831e896ff8003c87c682
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60745937"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server"></a>Mover dados do armazenamento de arquivos para um novo armazenamento de arquivos no Skype for Business Server

Se você precisar remover o servidor de arquivos que está atuando como o armazenamento de arquivos para sua implantação do Skype for Business Server, ou se precisar fazer outras alterações que indisponíveis o armazenamento de arquivos atual, primeiro você precisará criar um novo compartilhamento. Em seguida, você precisa executar as seguintes etapas:

1. Desligue os serviços Skype for Business Server que usam o armazenamento de arquivos que você planeja remover.

2. Defina o armazenamento de arquivos no Construtor de Topologias e publique as alterações para disponibilizar o novo armazenamento de arquivos para sua implantação.

3. Mova os dados para o novo armazenamento de arquivos.

4. Reinicie os servidores ou serviços.

5. Opcionalmente, remova o compartilhamento de arquivo antigo e a pasta de arquivo.

### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a>Para mover os dados do repositório de arquivos de um repositório para o novo

1. Faça logon em um computador como membro do grupo RTCUniversersalServerAdmins ou CsServerAdministrator onde o Skype for Business Server, Ferramentas Administrativas estão instalados.

2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle.

3. Na barra de navegação à esquerda, clique em **Topologia** e em **Status**.

4. Para cada pool de diretores, diretor, servidor Edição Standard e pool de Front-End que usa o armazenamento de arquivos que você planeja remover, selecione o servidor ou pool, clique em **Ação** e clique em **Parar todos os serviços**.

5. Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.

6. Iniciar Construtor de Topologias: clique em **Iniciar,** **clique** em Todos os Programas, Skype for Business Server **e** clique Skype for Business Server Construtor **de Topologias.**

7. Selecione um servidor ou pool que use o armazenamento de arquivos e faça o seguinte:

   a. Clique com o botão direito do mouse no servidor ou pool e clique em **Editar Propriedades**.

   b. Em **Editar propriedades,** em **Associações**, em **Armazenamento de arquivos,** clique em **Novo**.

   c. Em **Definir Novo Armazenamento de Arquivos,** em **FQDN** do servidor de arquivos, digite o FQDN (nome de domínio totalmente qualificado) do servidor de arquivos. Em **Compartilhamento de** arquivos, digite o nome da pasta para o novo compartilhamento de arquivos e clique em **OK**.

     > [!IMPORTANT]
     > Esta etapa define um novo armazenamento de arquivos para uso no Construtor de Topologias. Você o define apenas uma vez, não para cada servidor. Antes de publicar a topologia, você deve criar o compartilhamento de arquivos definido no servidor de arquivos especificado. Para detalhes, consulte [Define the File Store for the Front End](/previous-versions/office/communications/gg133895(v=ocs.14)).

8. Para cada servidor ou pool que usa o armazenamento de arquivos, faça o seguinte:

   a. Clique com o botão direito do mouse no servidor ou pool e clique em **Editar propriedades**.

   b. Em **Editar Propriedades,** em **Associações**, no **Armazenamento** de arquivos, selecione o novo compartilhamento de arquivos e clique em **OK**.

9. Publique a topologia, verifique o status da replicação e execute o Assistente Skype for Business Server implantação, conforme necessário. Para obter detalhes, consulte [Common Procedures for Removing Lync Servers and Components](/previous-versions/office/skype-server-2010/gg195688(v=ocs.14)).

10. Inicie um prompt de comando: clique em **Iniciar,** clique em **Executar** e digite cmd.exe.

11. Na linha de comando, digite o seguinte:

    ```console
    Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>
    ```

    > [!TIP]
    > A opção /S copia arquivos, diretórios e subdireções. A opção /XF ignora todos os arquivos chamados Meeting.Active. Versões atuais do robocopy.exe com a opção /MT aumentam muito a velocidade da cópia usando vários threads. Para a opção /LOG, use um caminho de diretório e o nome do arquivo de log na forma de C:\Logfiles\log.txt. Essa opção cria um arquivo de log de operações no local nomeado.

12. Quando a cópia de dados estiver concluída, no Painel de Controle do Lync Server, clique em **Topologia** e clique em **Status**.

13. Para cada servidor ou pool onde você parou serviços, selecione o servidor ou pool, clique em **Ação** e clique em **Iniciar todos os serviços.**

14. Remova o repositório de arquivos antigo da topologia e publique-a. Para detalhes, consulte [Remove a file store](/previous-versions/office/skype-server-2010/gg195635(v=ocs.14)).

15. (Opcional) Faça logon no computador que contém o repositório de arquivos que foi removido como membro do grupo Administradores local ou grupo Admins. de Domínio e remova o compartilhamento de arquivos e o diretório antigos.

## <a name="see-also"></a>Confira também

[Reatribuir um servidor para um repositório de arquivo diferente](/previous-versions/office/skype-server-2010/gg195633(v=ocs.14))

[Remover um armazenamento de arquivos](/previous-versions/office/skype-server-2010/gg195635(v=ocs.14))
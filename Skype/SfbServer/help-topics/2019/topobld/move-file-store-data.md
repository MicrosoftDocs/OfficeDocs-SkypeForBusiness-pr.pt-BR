---
title: Mover dados do armazenamento de arquivos para um novo armazenamento de arquivos no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8d1d5819-add2-4f5d-a436-74c00a281df0
ROBOTS: NOINDEX, NOFOLLOW
description: 'Se você precisar remover o servidor de arquivos que está atuando atualmente como o armazenamento de arquivos para sua implantação do Skype for Business Server, ou se precisar fazer outras alterações que tornariam o armazenamento de arquivos atual indisponível, primeiro será necessário criar um novo compartilhamento. Em seguida, você precisa executar as seguintes etapas:'
ms.openlocfilehash: 6121083d736075fa9ec58380dbc09ef6a8c4ef68
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49819601"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server"></a>Mover dados do armazenamento de arquivos para um novo armazenamento de arquivos no Skype for Business Server

Se você precisar remover o servidor de arquivos que está atuando atualmente como o armazenamento de arquivos para sua implantação do Skype for Business Server, ou se precisar fazer outras alterações que tornariam o armazenamento de arquivos atual indisponível, primeiro será necessário criar um novo compartilhamento. Em seguida, você precisa executar as seguintes etapas:

1. Desligue os serviços do Skype for Business Server que usam o armazenamento de arquivos que você planeja remover.

2. Defina o armazenamento de arquivos no Construtor de Topologias e publique as alterações para disponibilizar o novo armazenamento de arquivos para sua implantação.

3. Mova os dados para o novo armazenamento de arquivos.

4. Reinicie os servidores ou serviços.

5. Opcionalmente, remova o compartilhamento de arquivos e a pasta de arquivos antigos.

### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a>Para mover os dados do repositório de arquivos de um repositório para o novo

1. Faça logon em um computador como membro do grupo RTCUniversersalServerAdmins ou CsServerAdministrator onde o Skype for Business Server, Ferramentas Administrativas estão instalados.

2. Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.

3. Na barra de navegação à esquerda, clique em **Topologia** e em **Status**.

4. Para cada pool de Diretores, Diretor, servidor Standard Edition e pool de Front-End que usa o armazenamento de arquivos que você planeja remover, selecione o servidor ou pool, clique em Ação e clique em Parar todos os **serviços.**

5. Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.

6. Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click Skype for Business Server **Topology Builder**.

7. Selecione um servidor ou pool que usa o armazenamento de arquivos e faça o seguinte:

8. Clique com o botão direito do mouse no servidor ou pool e clique em **Editar Propriedades.**

9. In **Edit properties**, under **Associations**, under **File store**, click **New**.

10. Em **Definir Novo Armazenamento de Arquivos,** em **FQDN** do servidor de arquivos, digite o FQDN (nome de domínio totalmente qualificado) do servidor de arquivos. Em **Compartilhamento de** arquivos, digite o nome da pasta para o novo compartilhamento de arquivos e clique em **OK.**

     > [!IMPORTANT]
     > Esta etapa define um novo armazenamento de arquivos para uso no Construtor de Topologias. Você o define apenas uma vez, não para cada servidor. Antes de publicar a topologia, você deve criar o compartilhamento de arquivos definido no servidor de arquivos especificado. Para detalhes, consulte [Define the File Store for the Front End](https://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx).

11. Para cada servidor ou pool que usa o armazenamento de arquivos, faça o seguinte:

12. Clique com o botão direito do mouse no servidor ou pool e clique em **Editar propriedades.**

13. Em **Editar Propriedades**, em **Associações**, no **Armazenamento** de arquivos , selecione o novo compartilhamento de arquivo e clique em **OK**.

14. Publique a topologia, verifique o status de replicação e execute o Assistente de Implantação do Skype for Business Server conforme necessário. Para obter detalhes, consulte [Common Procedures for Removing Lync Servers and Components](https://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx).

15. Inicie um prompt de comando: clique em **Iniciar,** **clique** em Executar e digite cmd.exe.

16. Na linha de comando, digite o seguinte:

    ```console
    Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>
    ```

    > [!TIP]
    > A opção /S copia arquivos, diretórios e subdireários. A opção /XF ignora todos os arquivos chamados Meeting.Active. Versões atuais do robocopy.exe com a opção /MT aumentam muito a velocidade da cópia usando vários threads. Para a opção /LOG, use um caminho de diretório e um nome de arquivo de log na forma de C:\Logfiles\log.txt. Essa opção cria um arquivo de log de operações no local nomeado.

17. Quando a cópia de dados estiver concluída, no Painel de Controle do Lync Server, clique em **Topologia** e em **Status.**

18. Para cada servidor ou pool onde você interrompeu serviços, selecione o servidor ou pool, clique em Ação **e** clique em Iniciar todos **os serviços.**

19. Remova o repositório de arquivos antigo da topologia e publique-a. Para detalhes, consulte [Remove a file store](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx).

20. (Opcional) Faça logon no computador que contém o repositório de arquivos que foi removido como membro do grupo Administradores local ou grupo Admins. de Domínio e remova o compartilhamento de arquivos e o diretório antigos.

## <a name="see-also"></a>Confira também

[Reatribuir um servidor para um repositório de arquivo diferente](https://technet.microsoft.com/library/18509cce-a4d2-4537-a822-f99de6d7598e.aspx)

[Remover um armazenamento de arquivos](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)

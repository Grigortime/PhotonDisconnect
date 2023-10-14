using UnityEngine;
using Photon.Pun;
using Photon.Realtime;

public class AutoDisconnect : MonoBehaviourPunCallbacks
{
    private bool isDisconnecting = false;

    private void Start()
    {
        DisconnectPlayer();
    }

    private void DisconnectPlayer()
    {
        if (!isDisconnecting)
        {
            isDisconnecting = true;
            
            if (PhotonNetwork.InRoom)
            {
                PhotonNetwork.LeaveRoom();
            }
            else
            {
                PhotonNetwork.Disconnect();
            }
        }
    }

    public override void OnDisconnected(DisconnectCause cause)
    {
        isDisconnecting = false;
    }

    public override void OnLeftRoom()
    {
        base.OnLeftRoom();
        PhotonNetwork.Disconnect();
    }
}

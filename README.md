# C
movement- unity 1 : 
script  for camera :
 put the player at the transfomr :
 for Third person and First person :
 Engine = Unity : 
 ALM : 
----------------------------------------------------------------
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class cam1 : MonoBehaviour
{
    [SerializeReference] Transform player;

    float mousespeed = 360;
    float xRoutation = 12.5f;

    private void Start()
    {
        Cursor.lockState = CursorLockMode.Locked;
        Cursor.visible = false;
    }

    private void Update()
    {

        //camer rotation----------------------------------------------------------------
        float mouseX = Input.GetAxis("Mouse X");
        float mouseY = Input.GetAxis("Mouse Y");
        xRoutation -= mouseY;
        xRoutation = Mathf.Clamp(xRoutation, -30, 35);
        transform.localEulerAngles = new Vector3(xRoutation, 0, 0);
        player.Rotate(Vector3.up * mouseX * mousespeed * Time.deltaTime);
        //-------------------------------------------------------------------------------------------
    }

}



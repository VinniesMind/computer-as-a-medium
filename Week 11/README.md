# Week 11 Completed

//Enemy 3 Installment
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class Enemy3 : MonoBehaviour
{
    // Start is called before the first frame update
    void Start()
    {
        
    }

    // Update is called once per frame
    void Update()
    {
        transform.Translate(new Vector3(0, -1, 0) * Time.deltaTime * 4f);
        if (transform.position.y < -9f)
        {
            Destroy(this.gameObject);
        }
        
    }
}


//Changes made to GameManager
public GameObject enemyThreePrefab;

void Start()
{
    InvokeRepeating("CreateEnemyThree", 2, 4);
}

void CreateEnemyThree()
{
    Instantiate(enemyThreePrefab, new Vector3(Random.Range(-7f, 7f), 7.5f, 0), Quaternion.identity);
}
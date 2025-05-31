# Ex.No: 10 Implementation of 2D/3D game 
## NAME : ARUN KUMAR B
## REGISTER NUMBER : 212223230021

## AIM:
To develop a 2D game using C# program in unity .

## ALGORITHM:
# STEP 1:
 Create a 2D project in unity.

# STEP 2:
 Add player,hurdles,coins,track in the frame and add the valid collider2D component.

# STEP 3:
 Click Assets->Create-># Script.

# STEP 4:
 Create player.cs and coinmanger script and add c# code.

# STEP 5:
 Click canvas->Gamemanager->add Score and value.

# STEP 6:
 Drag the script to player and coin.

# STEP 7:
Run the scene and display the output.

## PROGRAM:

### PLAYERSCRIPT.CS
```
using System.Collections;
using System.Collections.Generic;
using System.Security.Cryptography;
using UnityEngine;
using UnityEngine.SocialPlatforms.Impl;

public class player : MonoBehaviour
{
    public float speed;
    public float jumpforce;
    private Rigidbody2D rb;
    public Score cc;
    // Start is called before the first frame update
    void Start()
    {
        rb = GetComponent<Rigidbody2D>();
    }

    // Update is called once per frame
    void Update()
    {
        float moveinp = Input.GetAxisRaw("Horizontal");
        transform.position += new Vector3(moveinp, 0, 0) * speed * Time.deltaTime;
        if (Input.GetKeyDown(KeyCode.Space) && Mathf.Abs(rb.linearVelocity.y) < 0.001f)
        {
            rb.AddForce(new Vector2(0, jumpforce), ForceMode2D.Impulse);
        }
    }
    private void OnTriggerEnter2D(Collider2D other)
    {
        if (other.CompareTag("Destroy"))
        {
            cc.coincount++;
            Destroy(other.gameObject);
        }
    }
}
```

### COINMANAGER.CS

```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using UnityEngine.UI;
public class Score : MonoBehaviour
{
    // Start is called before the first frame update
    public int coincount;
    public Text Value;
    // Start is called before the first frame update
    void Start()
    {

    }

    // Update is called once per frame
    void Update()
    {
        Value.text = coincount.ToString();
    }
}

```

## OUTPUT:
![Screenshot 2025-05-23 200113](https://github.com/user-attachments/assets/534028d8-0b5e-45a7-8033-db2c02adb44d)
![Screenshot 2025-05-23 200128](https://github.com/user-attachments/assets/5bc89c78-5ed6-4b4e-9545-5b66e4e34e2a)


## RESULT:

Thus a 2D game using C# program in unity is developed successfully.
